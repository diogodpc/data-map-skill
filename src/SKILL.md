---
name: data-map
description: >
  Generates a HubSpot Data Map spreadsheet for client onboarding engagements.
  A Data Map is the master field-mapping document that shows how fields from one
  or more source systems (e.g. Salesforce, Zendesk, a legacy CRM, a CSV export)
  translate to HubSpot native properties — across all objects (Contacts,
  Companies, Deals, Tickets, or custom objects) — in a single unified spreadsheet.

  Use this skill whenever a consultant says anything like:
  "create a data map", "build a data map", "I need a data map for [client]",
  "map the fields from [system] to HubSpot", "data mapping for [client]",
  "we're importing data from [system] to HubSpot", "help me map this data",
  "generate the field mapping spreadsheet", or any similar request to plan a
  HubSpot data migration or integration. Even if the user just says "map the
  data" or "set up the field mapping", trigger this skill.
---

# Data Map Generator

You are helping a Periti consultant create a **HubSpot Data Map** — a
structured spreadsheet that defines how fields from client source systems map
to HubSpot properties. This document guides the technical import/integration
work and is a key deliverable in every onboarding.

Read `references/hubspot_standard_fields.md` now — it contains the canonical
list of HubSpot native properties for each object you'll need to map to.

---

## Step 1 — Understand the client

Ask the user:

1. **Who is the client?** (company name and a one-line description of what they do)
2. **Which source systems are we mapping from?** (e.g. Salesforce, Zendesk, a legacy CRM, a spreadsheet) — get both the system name and which objects it holds
3. **Are there any custom or non-standard objects** that need to be included beyond Contacts, Companies, Deals, and Tickets?

While gathering this, do a quick web search on the client to understand their
industry, business model, and typical data needs. This context will inform the
"Industry best practice" column later.

---

## Step 2 — Collect source data files

Ask the user to upload one file per object per source system. Each file should
be a CSV or Excel export that contains at minimum the column headers (actual
data rows are helpful but not required).

**Naming convention to suggest to the user:**
`<SystemName>_<ObjectName>.csv` — e.g. `Salesforce_Contacts.csv`,
`Zendesk_Tickets.csv`

If filenames are ambiguous, ask the user to confirm which system and object
each file represents before proceeding.

Once you have the files, confirm with the user: "I've received the following
files — does this look right before I proceed?"

| File | System | Object |
|------|--------|--------|

---

## Step 3 — Extract fields from source files

For each uploaded file:

1. Read the header row to get all field/column names
2. If data rows are present, infer the likely **data type** for each field:
   - Text string → `Single-line text`
   - Long text / paragraphs → `Multi-line text`
   - Number (no decimals) → `Number (integer)`
   - Number (with decimals) → `Number (decimal)`
   - True/False, Yes/No, 0/1 → `Boolean (checkbox)`
   - Date only → `Date`
   - Date + time → `Date & time`
   - Email address pattern → `Email`
   - Phone number pattern → `Phone number`
   - URL / domain pattern → `URL`
   - Small set of repeated values → `Dropdown / select` (note the distinct values)
   - Currency pattern → `Number (currency)`
3. If no data rows exist, mark the type as `Unknown — confirm with client`

---

## Step 4 — Build the unified field list

This is the core of the skill. Your goal is a **single deduplicated list** of
fields across all systems and objects.

### Deduplication rules

Group fields by **HubSpot object** (Contact, Company, Deal, Ticket, or custom).
Within each object group, merge fields that represent the same concept, even if
named differently:

- `last_name`, `LastName`, `surname`, `family_name` → one row: **Last Name**
- `email`, `email_address`, `EmailAddress` → one row: **Email**
- `created_date`, `CreatedAt`, `date_created` → one row: **Create date**

Use semantic judgment — don't merge fields that merely sound similar but carry
different data (e.g. `billing_address` and `mailing_address` are distinct).

When merging, keep track of what each source system calls the field — this
populates the source system columns.

### Field ordering

Within each object, put the most fundamental identifying fields first
(name, email, phone, ID), then demographic/firmographic fields, then status
and lifecycle fields, then dates, then custom/niche fields.

---

## Step 5 — Map to HubSpot native properties

For each merged field, check `references/hubspot_standard_fields.md` and assign:

- **HubSpot field name** — the internal property name (e.g. `firstname`, `hs_lead_status`)
- **HubSpot field type** — the type as defined in HubSpot (e.g. `Single-line text`, `Dropdown`)
- **HubSpot field metadata** — for Dropdown/Radio/Checkbox types, list the standard option values

If a field maps cleanly to a HubSpot native property, use it. HubSpot native
properties are strongly preferred over custom properties because they power
built-in features (filters, reporting, lifecycle automation, etc.).

If no native property fits, write a snake_case suggested property name in the
**HubSpot field name** column (e.g. `subscription_tier`, `renewal_date`) and
set **Standard / Custom** to `Custom`. Set the type based on your inference
from Step 3.

---

## Step 6 — Industry best practice suggestions

Based on your research on the client (Step 1), think about what fields are
**typically important** for a company in their industry but may not appear in
any of the source systems.

Examples:
- B2B SaaS: `Product tier`, `MRR`, `Churn date`, `NPS score`, `Renewal date`
- E-commerce / retail: `Total orders`, `Average order value`, `Last purchase date`, `Loyalty tier`
- Professional services: `Engagement start date`, `Practice area`, `Account manager`
- Healthcare: `Patient type`, `Referral source`, `Insurance provider`
- Real estate: `Property type`, `Budget range`, `Pre-approval status`

For each suggestion:
- Add a new row with the HubSpot object it belongs to
- Leave all source system columns blank
- Put a brief rationale in the **Industry best practice** column explaining *why* this field matters for the client (e.g. "B2B SaaS — track subscription value for lifecycle segmentation")
- Map to a HubSpot native property if one exists, or suggest a custom property

Aim for 3–8 high-value suggestions per object. Don't pad with obvious generic
fields that are already covered by source data.

---

## Step 7 — Populate Notes and Transformations

Review each field and add:

**Notes** — any business rules or caveats:
- "Map to primary contact only if company has multiple contacts"
- "Source system uses numeric stage IDs — see transformation"
- "Field is required for deal creation"

**Transformations** — data conversion logic needed during import:
- Type conversions: "Convert Unix timestamp (ms) → ISO 8601 date"
- Value remapping: "Source values: 1=Hot, 2=Warm, 3=Cold → HubSpot: Hot Lead / Warm Lead / Cold Lead"
- Formatting: "Strip country code prefix (+1) from phone numbers"
- Derivations: "Concatenate first_name + ' ' + last_name → Full name"
- Normalisation: "Uppercase all country codes → ISO 3166-1 alpha-2"

Leave these blank if no transformation is needed.

---

## Step 8 — Generate the spreadsheet

Use the `xlsx` skill to produce the output file. The spreadsheet must have:

### Sheet: "Data Map"

One row per field. Columns in this exact order:

| # | Column | Notes |
|---|--------|-------|
| 1 | **Object** | HubSpot object name (Contact, Company, Deal, Ticket, or custom) |
| 2 | **Field Name** | Short plain-English name for the field (≤10 words, e.g. "Last name", "Company website") |
| 3–N | **[Source system name]** | One column per source system. Cell contains the field name in that system, or blank if the system doesn't have this field |
| N+1 | **Industry best practice** | Rationale if this is a suggested field; blank otherwise |
| N+2 | **HubSpot field name** | Internal property name only (e.g. `email`, `hs_lead_status`, `subscription_tier`) — no prefixes |
| N+3 | **Standard / Custom** | `Standard` if this is a native HubSpot property; `Custom` if a new property needs to be created |
| N+4 | **HubSpot field type** | e.g. Single-line text, Dropdown, Number, Date, Boolean |
| N+5 | **HubSpot field metadata** | Dropdown option values, or blank |
| N+6 | **Notes** | Business rules, caveats |
| N+7 | **Transformations** | Data conversion logic |

### Formatting

- **Freeze** the top header row
- **Bold** the header row; use a dark background (e.g. `#002B45` — Periti navy) with white text
- Group rows by object with alternating light background colours per object group to make it easy to scan (e.g. light blue for Contacts, light green for Companies, light yellow for Deals, light orange for Tickets)
- Auto-fit column widths (cap at 60 characters for readability)
- Add a subtle border between object groups
- Highlight "Industry best practice" rows with a distinct light purple background so they stand out

### Sheet: "Legend"

A second sheet with a short legend explaining the column headers, colour coding, and naming conventions used. Keep it concise — this is for handoff to clients or other team members.

---

## Output

Save the file as `<ClientName>_DataMap_<YYYY-MM-DD>.xlsx` in the outputs folder.

Present the file to the user and briefly summarise:
- Total number of fields mapped
- How many mapped to HubSpot native properties vs. custom
- How many industry best practice suggestions were added
- Any fields flagged as needing client confirmation

---

## Quality checklist (review before handing off)

- [ ] No duplicate rows for the same concept within the same object
- [ ] Every row has a HubSpot field name (no `[Custom]` prefixes — use the Standard/Custom column instead)
- [ ] Standard / Custom column is filled for every row
- [ ] Source system columns are populated correctly (blank ≠ wrong)
- [ ] Dropdown fields have values listed in the metadata column
- [ ] Industry best practice rows are clearly justified
- [ ] Transformations are specific enough for a developer to implement
