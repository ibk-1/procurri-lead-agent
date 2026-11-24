---
name: it-leads-brief
description: >
  This skill should be used when the user asks to "brief me on" a company,
  "prepare me for a call with" a prospect, "run /it-leads-brief", or wants
  background on a lead from their IT lead sheet before contacting them.
  It produces a short, sourced pre-call brief on one company.
metadata:
  version: "0.1.0"
---

# Pre-call brief

Produce a one-screen brief on one company so a salesperson can hold a
first conversation. The company name comes from the request. If it is on the
user's lead sheet, start from that row.

## Rules

- Research on the open web only. Never open LinkedIn or Sales Navigator, and
  never contact the company.
- Every fact carries its source. Say "not found" instead of guessing.
- Name people only in the business roles public sources give them. No private
  details, no personal contact data.
- Offer only services listed under services to offer in the lead sheet's
  Config tab. Without a sheet, use the defaults in
  `../it-leads-run/references/sheet-layout.md`.

## Research (about 8 searches, 8 page reads)

1. The company's own site: what it does, size, locations, IT or data centre
   footprint if stated.
2. News from the last 12 months on IT, data centres, cloud, mergers, funding.
3. Open jobs in infrastructure, data centre or IT asset roles.
4. Sustainability or ESG statements on IT, e-waste or circularity.
5. For partners: what they resell and to whom.

## Output

Reply in the conversation, in the language the user wrote in:

- **In one line:** who they are and why now.
- **The trigger:** the event, with date and source.
- **What they probably have or need:** hardware estate or demand, marked as
  stated or inferred.
- **Who owns it:** job titles, and names only where public sources give them.
- **Our angle:** the one or two services that fit, and one that does not.
- **Three questions to ask** that a person who read the source would ask.
- **Risks:** what is unknown, what could make this a non-lead.
- **Sources:** links.

Keep it under 250 words before the sources. Do not create a document unless
the user asks for one.
