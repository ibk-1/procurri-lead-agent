# Test run report

**Date:** 14 November 2026 · **Version:** 0.1.0 · **Result:** passed, with
two limitations (tenders, and parts not yet tested end to end).

## What was tested

One full lead run, following `skills/it-leads-run/SKILL.md` step by step,
into a fresh sheet built to
`skills/it-leads-run/references/sheet-layout.md`.

Test settings (Config tab): Territory Germany · all four plays · German notes
· maximum 10 leads · excluded companies: Medialine AG, 8its GmbH ·
watchlist: noris network AG, Polarise.

Effort: 15 web searches, 22 page reads attempted (16 readable).

## Leads produced

| Company | Type | Play | Priority | Source date | Note length |
|---|---|---|---|---|---|
| Connexta | Partner | MSP | 1 | 2 Nov 2026 | 286 |
| Polarise | Buyer | GPU | 1 | 22 Oct 2026 | 248 |
| HARTING Technologiegruppe | Seller | Migration | 2 | 18 Sep 2026 | 247 |
| Karlsruhe Institute of Technology | Seller | GPU | 3 | 29 Sep 2026 | no outreach (public body) |

Four leads against a limit of ten. The run is allowed to return fewer, and
did.

## Checks

| Check | Result |
|---|---|
| Every lead has a source that was opened and read | Pass (4 of 4) |
| Signal text contains only facts from the source | Pass; unknowns are stated ("the source does not say where the ERP runs today") |
| Publication date and event date recorded separately | Pass |
| Source within 60 days, or event still running | Pass (oldest: 57 days) |
| LinkedIn notes 300 characters or fewer, counted with code | Pass (286, 248, 247) |
| Notes in German, one event, one service, one question | Pass |
| No service from "Services not to offer" in any draft | Pass (no maintenance offered) |
| Names only where the source gives a business role | Pass |
| Excluded companies skipped | Pass: 8its and Medialine appeared in search results and were not listed |
| Watchlist re-checked and updated | Pass: Polarise produced a lead; noris network had no new event and is marked so |
| Run log written | Pass |
| Nothing sent, LinkedIn not opened | Pass |

## Candidates rejected, and why

| Candidate | Reason |
|---|---|
| Nobix / Albakom | Source from February 2026, older than 60 days |
| UmweltBank with noris network | Source from 2024 |
| Nokia, RISE with SAP | Outside the territory |
| Schwarz Digits, RISE with SAP on STACKIT | A provider's product launch; no customer event |
| Percano Group | No link to hardware in the source |
| QualityHosting / Be-Cloud | Microsoft cloud services only; no link to hardware |
| Universität Paderborn, Otus expansion | Purchase contract already awarded |
| Three tender notices | Deadline passed, or unrelated to IT disposal |

## Limitations found

1. **Public tenders returned nothing.** TED refuses automated reading, and the
   notices that could be opened had closed or were unrelated. The play is kept,
   with a rule that a tender counts only when its notice was actually read.
   Practical workaround: set up the tender portals' own email alerts (TED,
   DTVP) for terms such as "Datenlöschung" and "IT-Altgeräte".
2. **Public institutions surfaced in a non-tender play** (KIT in the GPU
   play). The first draft of the rules did not cover this. Fixed in
   `plays.md`: public bodies are always Priority 3 with no outreach note
   unless a tender is open.
3. **Migration leads are thin.** Many announcements do not say where systems
   run today. The play produced one Priority 2 lead; the note asks instead of
   assuming.

## Not yet tested

These need a real account with the plugin installed and should be checked by
the first pilot user:

- Installing from the repository through **Customize → Plugins → Add
  marketplace** (the route is taken from Anthropic's documentation).
- The `/it-leads-setup` conversation and the scheduled task it creates.
- A scheduled run firing unattended.
- The learning step, which needs at least five rows with a Status set.
- The optional Sales Navigator alert-email step.
- `/it-leads-brief`.

## Pilot acceptance criteria (suggested)

After four weekly runs with one salesperson:

- at least 3 leads per run that the salesperson judges worth contacting;
- no lead without a working source link;
- no duplicate companies for the same event;
- at least one reply or meeting from leads contacted.
