# How it works

## The three parts

| Part | What it is | Here |
|---|---|---|
| Agent | Claude doing a multi-step research job on its own | The lead run: search, read, filter, classify, draft, write |
| Schedule | A timer that starts the job | One weekly scheduled task per salesperson |
| Plugin | A package others can install | This repository |

There is no code, database or server. The agent's behaviour is defined by the
instruction files under `skills/`. Each salesperson's data lives in their own
lead sheet.

## What happens in one run

```
Scheduled task (weekly)
        │
        ▼
1. Load the sheet ──► Config, existing Leads, Watchlist, Run log
2. Learn          ──► which plays and company types got replies
3. Research       ──► Discovery (new companies, per play)
                      Watchlist (saved accounts, every 14 days)
                      Alert emails (optional, read-only hints)
4. Filter         ──► duplicates, excluded, too old, wrong territory,
                      no real hardware link, competitors
5. Classify       ──► type, play, priority, contact title,
                      Sales Navigator search, LinkedIn note
6. Write          ──► append rows to Leads, one row to Run log
7. Report         ──► short summary, notification for Priority 1
        │
        ▼
Salesperson: finds the person in Sales Navigator, sends by hand, sets Status
        │
        └──────► Status and My notes feed step 2 of the next run
```

## Where leads come from

The agent starts from **events**, not from company lists. A company is a lead
in the months around an event that creates a need:

- **Trade press and press releases:** channelpartner.de, it-business.de,
  datacenter-insider.de, cio.de, computerwoche.de, it-daily.net,
  datacenterdynamics.com, and companies' own news pages.
- **Tender portals:** TED for the EU, oeffentlichevergabe.de, dtvp.de and
  evergabe-online.de for Germany, USP for Austria, simap.ch for Switzerland.
- **Your watchlist:** accounts you add, typically from your Sales Navigator
  lists.

The exact signals and search terms per play are in
[`skills/it-leads-run/references/plays.md`](../skills/it-leads-run/references/plays.md).

## Where Sales Navigator fits

Sales Navigator has no export and no API for individual seats, and automating
it breaks LinkedIn's terms. So the split is:

| The agent | You, in Sales Navigator |
|---|---|
| Finds the company and the reason to call now | Find the person, using the search recipe in the row |
| Names the job title that owns the problem | Save the account and lead to your lists |
| Drafts the note | Send it |
| Re-checks your watchlist | Add saved accounts to the watchlist |

## How a lead is prioritised

- **Priority 1:** fresh source (30 days) or an event still ahead, a clear link
  to a service the company offers, a reachable company, and a contact title that owns
  the problem.
- **Priority 2:** a real signal with one weakness, such as a very large
  company or an unstated hardware link.
- **Priority 3:** worth watching, not worth contacting yet.

## How it improves

You set **Status** (New, Contacted, Replied, Meeting, Not a fit, Later) and
write a reason in **My notes** when a lead is not a fit. Once at least five
rows are marked, each run leans toward what got replies and away from what you
rejected, and says so in the Run log.

## Limits

- It only sees what is published. A quiet hardware refresh is invisible.
- The link from an event to hardware is often an inference. Rows say so, and
  notes ask instead of assuming.
- Web search results vary from run to run. It works as a weekly habit, not as
  a one-time sweep of the market.
- It names job titles. Finding the person is your step.

## Changing the agent

| To change | Edit |
|---|---|
| Signals, search terms, sources, priority rules | `skills/it-leads-run/references/plays.md` |
| Note style, length, language rules | `skills/it-leads-run/references/outreach.md` |
| Sheet columns and default settings | `skills/it-leads-run/references/sheet-layout.md` |
| The steps of a run and the hard rules | `skills/it-leads-run/SKILL.md` |
| The setup conversation | `skills/it-leads-setup/SKILL.md` |

After a change: raise `version` in `.claude-plugin/plugin.json`, add a line to
`CHANGELOG.md`, run `claude plugin validate .` if you have Claude Code, and
push to the default branch.
