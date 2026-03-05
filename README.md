# data-map

A [Cowork](https://claude.ai) skill that automates HubSpot data map creation for onboarding engagements. Given source system exports (CSV/Excel), it deduplicates fields across systems and objects, maps them to HubSpot native properties, flags custom property requirements, and suggests industry-relevant fields based on client research — outputting a formatted Excel deliverable ready for handoff.

---

## What it does

When a Periti consultant is onboarding a client into HubSpot, this skill takes the raw data exports from one or more source systems and produces a single, structured **Data Map spreadsheet** that defines:

- Which fields exist across all source systems (deduplicated)
- How each field maps to a HubSpot native property (or what custom property to create)
- What data transformations are needed during import
- Which additional fields are recommended based on the client's industry

## Output

An `.xlsx` file with two sheets:

**Data Map** — one row per field, with these columns:

| Column | Description |
|--------|-------------|
| Object | HubSpot object (Contact, Company, Deal, Ticket, or custom) |
| Field Name | Plain-English name for the field |
| *[Source system]* | One column per source system — shows the original field name |
| Industry best practice | Rationale for suggested fields not present in any source |
| HubSpot field name | Internal HubSpot property name (e.g. `firstname`, `hs_lead_status`) |
| Standard / Custom | Whether the property is native to HubSpot or needs to be created |
| HubSpot field type | e.g. Single-line text, Dropdown, Number, Date |
| HubSpot field metadata | Valid option values for Dropdown/Radio/Checkbox fields |
| Notes | Business rules or caveats |
| Transformations | Data conversion logic (type casts, value remaps, formatting) |

**Legend** — a concise reference sheet explaining column headers, colour coding, and naming conventions for client handoff.

## Trigger phrases

The skill activates when you say things like:

- "create a data map for [client]"
- "build a data map"
- "map the fields from [system] to HubSpot"
- "data mapping for [client]"
- "we're importing data from [system] to HubSpot"
- "generate the field mapping spreadsheet"

## Usage

1. Install `data-map.skill` in Cowork
2. Tell Claude who the client is and which systems you're migrating from
3. Upload your source data files (CSV or Excel exports, one file per object per system)
4. Claude researches the client, processes the files, and produces the data map

**Recommended file naming:** `<SystemName>_<ObjectName>.csv` — e.g. `Salesforce_Contacts.csv`, `Zendesk_Tickets.csv`

## What's bundled

```
data-map/
├── SKILL.md                              # Skill instructions (8-step workflow)
└── references/
    └── hubspot_standard_fields.md        # Canonical HubSpot native properties
                                          # for Contacts, Companies, Deals, Tickets
```

## Requirements

- [Claude Cowork](https://claude.ai) desktop app
- Source data files in CSV or Excel format (headers required; data rows optional but improve type inference)
