# Changelog

## 0.2.0 (2026-11-24)

- Renamed to **IT Lead Agent** (`it-lead-agent`). Commands are now
  `/it-leads-setup`, `/it-leads-run` and `/it-leads-brief`.
- All documentation and instructions use neutral wording; no company is
  named as the client.

## 0.1.2 (2026-11-23)

Documentation only.

- README, step-by-step guide and "How I built it" rewritten to be short and
  plain for non-technical readers.
- README lists the sources behind each test lead and asks readers which
  sources they would add.

## 0.1.1 (2026-11-23)

Documentation only; the agent's behaviour is unchanged.

- README rewritten for newcomers: why it is built this way, sources, plays,
  flow diagram, lead sheet, install, test results, rules, FAQ.
- New `docs/HOW-I-BUILT-IT.md` for non-technical readers.
- New `docs/GETTING-STARTED.md` (replaces `docs/INSTALL.md`): from the
  shared link to the first leads, with every setup question, defaults,
  example answers, the Sales Navigator step and troubleshooting.
- README: "Start here" section for people who were sent the link.
- Clear note that this is an independent student proposal, not a company
  product.

## 0.1.0 (2026-11-14)

First pilot version.

- `it-leads-setup`: creates a per-person lead sheet and a weekly scheduled
  task.
- `it-leads-run`: weekly research across four plays (migration → disposal,
  MSPs → partnership, GPU build-outs, public tenders), with discovery,
  watchlist re-checks and optional read-only Sales Navigator alert emails.
- `it-leads-brief`: sourced pre-call brief on one company.
- Lead sheet with Leads, Watchlist, Config and Run log tabs.
- German LinkedIn notes by default, 300 characters or fewer.
- Third-party maintenance excluded from drafts until the company confirms it.
