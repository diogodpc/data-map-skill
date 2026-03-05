# HubSpot Standard (Native) Properties

This reference lists the most important HubSpot native properties per object.
Always prefer these over custom properties when a field semantically matches.

---

## CONTACTS

| HubSpot field name | Label | Type | Metadata / options |
|---|---|---|---|
| `firstname` | First name | Single-line text | |
| `lastname` | Last name | Single-line text | |
| `email` | Email | Email | |
| `phone` | Phone number | Phone number | |
| `mobilephone` | Mobile phone number | Phone number | |
| `fax` | Fax number | Phone number | |
| `jobtitle` | Job title | Single-line text | |
| `company` | Company name | Single-line text | |
| `website` | Website URL | URL | |
| `address` | Street address | Single-line text | |
| `city` | City | Single-line text | |
| `state` | State/Region | Single-line text | |
| `zip` | Postal code | Single-line text | |
| `country` | Country/Region | Single-line text | |
| `salutation` | Salutation | Dropdown | Mr.; Mrs.; Miss; Ms.; Dr.; Prof. |
| `gender` | Gender identity | Dropdown | Male; Female; Non-binary; Other; Prefer not to say |
| `date_of_birth` | Date of birth | Date | |
| `hs_language` | Preferred language | Single-line text | |
| `lifecyclestage` | Lifecycle stage | Dropdown | subscriber; lead; marketingqualifiedlead; salesqualifiedlead; opportunity; customer; evangelist; other |
| `hs_lead_status` | Lead status | Dropdown | NEW; OPEN; IN_PROGRESS; OPEN_DEAL; UNQUALIFIED; ATTEMPTED_TO_CONTACT; CONNECTED; BAD_TIMING |
| `hubspot_owner_id` | Contact owner | HubSpot user | |
| `hs_persona` | Persona | Dropdown | (custom per portal) |
| `message` | Message | Multi-line text | |
| `notes_last_contacted` | Last contacted | Date & time | |
| `notes_last_updated` | Last activity date | Date & time | |
| `notes_next_activity_date` | Next activity date | Date & time | |
| `num_contacted_notes` | Number of times contacted | Number | |
| `num_notes` | Number of sales activities | Number | |
| `hs_email_optout` | Unsubscribed from all email | Boolean | |
| `hs_emailconfirmationstatus` | Marketing email confirmation | Dropdown | double_opt_in_pending; confirmed |
| `hs_content_membership_status` | Membership status | Dropdown | active; inactive |
| `hs_buying_role` | Buying role | Multi-select | BLOCKER; BUDGET_HOLDER; CHAMPION; DECISION_MAKER; END_USER; EXECUTIVE_SPONSOR; INFLUENCER; LEGAL_COMPLIANCE; PRACTITIONER |
| `createdate` | Create date | Date & time | |
| `lastmodifieddate` | Last modified date | Date & time | |
| `hs_analytics_source` | Original source | Dropdown | DIRECT_TRAFFIC; ORGANIC_SEARCH; PAID_SEARCH; REFERRALS; SOCIAL_MEDIA; EMAIL_MARKETING; PAID_SOCIAL; OTHER_CAMPAIGNS; OFFLINE |
| `hs_analytics_first_url` | First page seen | URL | |
| `hs_analytics_last_url` | Last page seen | URL | |
| `recent_conversion_date` | Recent conversion date | Date & time | |
| `hs_object_id` | Record ID | Number | |

---

## COMPANIES

| HubSpot field name | Label | Type | Metadata / options |
|---|---|---|---|
| `name` | Company name | Single-line text | |
| `domain` | Company domain name | URL | |
| `phone` | Phone number | Phone number | |
| `address` | Street address | Single-line text | |
| `address2` | Street address 2 | Single-line text | |
| `city` | City | Single-line text | |
| `state` | State/Region | Single-line text | |
| `zip` | Postal code | Single-line text | |
| `country` | Country/Region | Single-line text | |
| `website` | Website URL | URL | |
| `description` | Description | Multi-line text | |
| `industry` | Industry | Dropdown | ACCOUNTING; AIRLINES_AVIATION; ALTERNATIVE_DISPUTE_RESOLUTION; ALTERNATIVE_MEDICINE; ANIMATION; APPAREL_FASHION; ARCHITECTURE_PLANNING; ARTS_CRAFTS; AUTOMOTIVE; BANKING; BIOTECHNOLOGY; BROADCAST_MEDIA; BUILDING_MATERIALS; BUSINESS_SUPPLIES_AND_EQUIPMENT; CAPITAL_MARKETS; CHEMICALS; CIVIC_SOCIAL_ORGANIZATION; CIVIL_ENGINEERING; COMPUTER_GAMES; COMPUTER_HARDWARE; COMPUTER_NETWORKING; COMPUTER_SOFTWARE; CONSTRUCTION; CONSUMER_ELECTRONICS; CONSUMER_GOODS; CONSUMER_SERVICES; COSMETICS; DAIRY; DEFENSE_SPACE; DESIGN; EDUCATION_MANAGEMENT; ELEARNING; ELECTRICAL_ELECTRONIC_MANUFACTURING; ENTERTAINMENT; ENVIRONMENTAL_SERVICES; EVENTS_SERVICES; EXECUTIVE_OFFICE; FACILITIES_SERVICES; FARMING; FINANCIAL_SERVICES; FINE_ART; FISHERY; FOOD_BEVERAGES; FOOD_PRODUCTION; FUND_RAISING; FURNITURE; GAMBLING_CASINOS; GLASS_CERAMICS_CONCRETE; GOVERNMENT_ADMINISTRATION; GOVERNMENT_RELATIONS; GRAPHIC_DESIGN; HEALTH_WELLNESS_AND_FITNESS; HIGHER_EDUCATION; HOSPITAL_HEALTH_CARE; HOSPITALITY; HUMAN_RESOURCES; IMPORT_AND_EXPORT; INDIVIDUAL_FAMILY_SERVICES; INDUSTRIAL_AUTOMATION; INFORMATION_SERVICES; INFORMATION_TECHNOLOGY_AND_SERVICES; INSURANCE; INTERNATIONAL_AFFAIRS; INTERNATIONAL_TRADE_AND_DEVELOPMENT; INTERNET; INVESTMENT_BANKING; INVESTMENT_MANAGEMENT; JUDICIARY; LAW_ENFORCEMENT; LAW_PRACTICE; LEGAL_SERVICES; LEGISLATIVE_OFFICE; LEISURE_TRAVEL_TOURISM; LIBRARIES; LOGISTICS_AND_SUPPLY_CHAIN; LUXURY_GOODS_JEWELRY; MACHINERY; MANAGEMENT_CONSULTING; MARITIME; MARKETING_AND_ADVERTISING; MARKET_RESEARCH; MECHANICAL_OR_INDUSTRIAL_ENGINEERING; MEDIA_PRODUCTION; MEDICAL_DEVICES; MEDICAL_PRACTICE; MENTAL_HEALTH_CARE; MILITARY; MINING_METALS; MOTION_PICTURES_AND_FILM; MUSEUMS_AND_INSTITUTIONS; MUSIC; NANOTECHNOLOGY; NEWSPAPERS; NON_PROFIT_ORGANIZATION_MANAGEMENT; OIL_ENERGY; ONLINE_MEDIA; OUTSOURCING_OFFSHORING; PACKAGE_FREIGHT_DELIVERY; PACKAGING_AND_CONTAINERS; PAPER_FOREST_PRODUCTS; PERFORMING_ARTS; PHARMACEUTICALS; PHILANTHROPY; PHOTOGRAPHY; PLASTICS; POLITICAL_ORGANIZATION; PRIMARY_SECONDARY_EDUCATION; PRINTING; PROFESSIONAL_TRAINING_COACHING; PROGRAM_DEVELOPMENT; PUBLIC_POLICY; PUBLIC_RELATIONS_AND_COMMUNICATIONS; PUBLIC_SAFETY; PUBLISHING; RAILROAD_MANUFACTURE; RANCHING; REAL_ESTATE; RECREATIONAL_FACILITIES_AND_SERVICES; RELIGIOUS_INSTITUTIONS; RENEWABLES_ENVIRONMENT; RESEARCH; RESTAURANTS; RETAIL; SECURITY_AND_INVESTIGATIONS; SEMICONDUCTORS; SHIPBUILDING; SPORTING_GOODS; SPORTS; STAFFING_AND_RECRUITING; SUPERMARKETS; TELECOMMUNICATIONS; TEXTILES; THINK_TANKS; TOBACCO; TRANSLATION_AND_LOCALIZATION; TRANSPORTATION_TRUCKING_RAILROAD; UTILITIES; VENTURE_CAPITAL_PRIVATE_EQUITY; VETERINARY; WAREHOUSING; WHOLESALE; WINE_AND_SPIRITS; WIRELESS; WRITING_EDITING |
| `type` | Type | Dropdown | ANALYST; COMPETITOR; DISTRIBUTOR; INTEGRATOR; INVESTOR; PARTNER; PRESS; PROSPECT; RESELLER; OTHER |
| `numberofemployees` | Number of employees | Number | |
| `annualrevenue` | Annual revenue | Number | |
| `total_revenue` | Total revenue | Number | |
| `founded_year` | Year founded | Single-line text | |
| `hubspot_owner_id` | Company owner | HubSpot user | |
| `lifecyclestage` | Lifecycle stage | Dropdown | subscriber; lead; marketingqualifiedlead; salesqualifiedlead; opportunity; customer; evangelist; other |
| `hs_lead_status` | Lead status | Dropdown | NEW; OPEN; IN_PROGRESS; OPEN_DEAL; UNQUALIFIED; ATTEMPTED_TO_CONTACT; CONNECTED; BAD_TIMING |
| `createdate` | Create date | Date & time | |
| `hs_lastmodifieddate` | Last modified date | Date & time | |
| `notes_last_contacted` | Last contacted | Date & time | |
| `notes_next_activity_date` | Next activity date | Date & time | |
| `num_associated_contacts` | Associated contacts | Number | |
| `hs_object_id` | Record ID | Number | |
| `hs_analytics_source` | Original source | Dropdown | (same as contacts) |
| `linkedin_company_page` | LinkedIn company page | URL | |
| `twitterhandle` | Twitter handle | Single-line text | |
| `facebook_company_page` | Facebook page | URL | |
| `googleplus_page` | Google+ page | URL | |
| `hs_parent_company_id` | Parent company | Number | |

---

## DEALS

| HubSpot field name | Label | Type | Metadata / options |
|---|---|---|---|
| `dealname` | Deal name | Single-line text | |
| `amount` | Amount | Number | |
| `dealstage` | Deal stage | Dropdown | (pipeline-specific — confirm with client) |
| `pipeline` | Pipeline | Dropdown | (portal-specific — confirm with client) |
| `closedate` | Close date | Date | |
| `dealtype` | Deal type | Dropdown | newbusiness; existingbusiness |
| `description` | Description | Multi-line text | |
| `hubspot_owner_id` | Deal owner | HubSpot user | |
| `hs_priority` | Priority | Dropdown | low; medium; high |
| `hs_deal_stage_probability` | Probability | Number | |
| `hs_forecast_amount` | Forecast amount | Number | |
| `hs_forecast_category` | Forecast category | Dropdown | omit; pipeline; best_case; commit; closed |
| `hs_acv` | Annual contract value | Number | |
| `hs_arr` | Annual recurring revenue | Number | |
| `hs_mrr` | Monthly recurring revenue | Number | |
| `hs_tcv` | Total contract value | Number | |
| `hs_projected_amount` | Projected amount | Number | |
| `num_associated_contacts` | Number of contacts | Number | |
| `createdate` | Create date | Date & time | |
| `notes_last_contacted` | Last contacted | Date & time | |
| `notes_last_updated` | Last activity date | Date & time | |
| `notes_next_activity_date` | Next activity date | Date & time | |
| `closed_lost_reason` | Closed lost reason | Single-line text | |
| `closed_won_reason` | Closed won reason | Single-line text | |
| `hs_object_id` | Record ID | Number | |
| `hs_num_of_associated_line_items` | Number of line items | Number | |
| `hs_is_closed` | Is deal closed? | Boolean | |
| `hs_is_closed_won` | Is closed won? | Boolean | |

---

## TICKETS

| HubSpot field name | Label | Type | Metadata / options |
|---|---|---|---|
| `subject` | Ticket name | Single-line text | |
| `content` | Ticket description | Multi-line text | |
| `hs_pipeline` | Pipeline | Dropdown | (portal-specific) |
| `hs_pipeline_stage` | Ticket status | Dropdown | (pipeline-specific) |
| `hs_ticket_priority` | Priority | Dropdown | LOW; MEDIUM; HIGH; URGENT |
| `hs_ticket_category` | Category | Dropdown | PRODUCT_ISSUE; BILLING_ISSUE; FEATURE_REQUEST; GENERAL_INQUIRY; OTHER |
| `hubspot_owner_id` | Ticket owner | HubSpot user | |
| `hs_resolution` | Resolution | Multi-line text | |
| `source_type` | Source | Dropdown | EMAIL; FORM; PHONE; CHAT; SOCIAL_MEDIA; IN_PERSON |
| `hs_createdate` | Create date | Date & time | |
| `hs_lastmodifieddate` | Last modified date | Date & time | |
| `closed_date` | Close date | Date & time | |
| `time_to_first_response_date` | Time to first response | Number | |
| `time_to_close` | Time to close | Number | |
| `num_associated_contacts` | Associated contacts | Number | |
| `hs_object_id` | Record ID | Number | |
| `hs_num_times_contacted` | Number of times contacted | Number | |

---

## NOTES ON CUSTOM OBJECTS

For custom objects, there are no native property names to reference. Instead:
- Use snake_case for internal names (e.g. `subscription_tier`, `contract_start_date`)
- Prefix with a short namespace if the portal already has many custom objects
- Always include: a unique ID field, a display name field, and a created date field
- The "primary display property" (shown in the record title) must be defined at schema creation time

---

## COMMON CROSS-OBJECT FIELDS

These appear in multiple objects and should be mapped consistently:

| Concept | Contact field | Company field | Deal field | Ticket field |
|---|---|---|---|---|
| Owner | `hubspot_owner_id` | `hubspot_owner_id` | `hubspot_owner_id` | `hubspot_owner_id` |
| Create date | `createdate` | `createdate` | `createdate` | `hs_createdate` |
| Last modified | `lastmodifieddate` | `hs_lastmodifieddate` | `hs_lastmodifieddate` | `hs_lastmodifieddate` |
| Lifecycle stage | `lifecyclestage` | `lifecyclestage` | — | — |
| Record ID | `hs_object_id` | `hs_object_id` | `hs_object_id` | `hs_object_id` |
