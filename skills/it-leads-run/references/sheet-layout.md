# Lead sheet layout

Each salesperson has one lead sheet, a Claude Sheets artifact created by
`it-leads-setup`. It has four tabs. Tab and column names are fixed; the skills
find things by these names.

## Tab: Leads

One row per lead. Row 1 is the header.

| Col | Header | Written by | Content |
|---|---|---|---|
| A | Company | agent | Company name |
| B | Type | agent | Seller, Buyer, Partner or Both |
| C | Priority | agent | 1, 2 or 3 |
| D | Signal | agent | What happened, 1 to 2 sentences, facts from the source only |
| E | LinkedIn note | agent | Draft, 300 characters or fewer |
| F | Status | **salesperson** | New, Contacted, Replied, Meeting, Not a fit, Later |
| G | My notes | **salesperson** | Free text; why not a fit, what was said |
| H | Who to contact | agent | Job title; a name only if the source names the person |
| I | Sales Navigator search | agent | Search recipe |
| J | Why it fits | agent | One line: which service fits and any caveat |
| K | Play | agent | Migration, MSP, GPU or Tender |
| L | Published | agent | Source publication date |
| M | Event date | agent | Date of the event itself if stated, else blank |
| N | Source | agent | URL that was read |
| O | Added | agent | Date the row was added |

The agent sets Status to `New` once, when it adds the row, and never writes to
columns F or G again.

Formatting: header fill, table declared on A:O, row 1 and column A frozen,
wrap on D, E, H, I, J, dropdowns on B and F. Suggested widths: A 180, D 300,
E 340, G 200, H 200, I 260, J 220, N 180.

Status dropdown options: New, Contacted, Replied, Meeting, Not a fit, Later.
Type dropdown options: Seller, Buyer, Partner, Both.

## Tab: Watchlist

Accounts the salesperson wants re-checked, usually copied from their Sales
Navigator account lists.

| Col | Header | Written by |
|---|---|---|
| A | Company | salesperson |
| B | Website | salesperson (optional) |
| C | Why watching | salesperson (optional) |
| D | Last checked | agent |
| E | Last finding | agent |

## Tab: Config

Two columns: Setting (A) and Value (B). The salesperson may edit values at any
time; the next run uses them.

| Setting | Default | Meaning |
|---|---|---|
| Owner | (set at setup) | Whose sheet this is |
| Territory | Germany | Countries or regions to search |
| Plays | Migration, MSP, GPU, Tender | Which plays to run |
| Note language | German | German or English |
| Max leads per run | 10 | Upper limit, never a target |
| Services to offer | ITAD and certified data erasure; hardware buy-back; refurbished enterprise hardware and spare parts; GPU sourcing and buy-back; data centre services | What a draft may offer |
| Services not to offer | Third-party maintenance (not confirmed) | What a draft must not offer |
| Excluded companies | (blank) | Existing customers, competitors, anyone not to be listed |
| Read Sales Navigator alert emails | No | Yes only if the salesperson has connected email and wants this |

## Tab: Run log

| Col | Header |
|---|---|
| A | Date |
| B | New leads |
| C | Plays run |
| D | Notes |

One row per run, newest at the bottom.
