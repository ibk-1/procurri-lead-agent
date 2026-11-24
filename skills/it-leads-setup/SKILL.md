---
name: it-leads-setup
description: >
  This skill should be used when the user asks to "set up the IT lead
  agent", "run /it-leads-setup", "install the lead agent for me", "create my
  lead sheet", or wants to change the schedule of their weekly IT lead
  run. It creates the user's own lead sheet and schedules the weekly run.
metadata:
  version: "0.1.0"
---

# IT lead agent setup

Set up one salesperson: create their lead sheet, fill in their settings, and
schedule the weekly run. This takes one short conversation.

## Step 1: Check for an existing setup

List the user's artifacts and scheduled tasks. If a sheet named
`IT Leads – <name>` or a task named `IT leads (weekly)` already
exists, say so and ask whether to keep it, change it, or start fresh. Never
create a second sheet or a second task without the user saying so.

## Step 2: Ask four things

Ask together, with sensible defaults offered:

1. **Territory.** Germany (default), Austria, Switzerland, or specific regions.
2. **Plays.** Migration → disposal, MSPs → partnership, GPU build-outs, Public
   tenders. Default: all four.
3. **Note language.** German (default) or English.
4. **Run time.** Day and time for the weekly run. Default: Monday morning.

Then ask, as optional free text: companies to exclude (existing customers,
competitors), and any accounts to put on the watchlist now.

## Step 3: Create the lead sheet

Create a new Sheets artifact titled `IT Leads – <user's first name>`.
Build the four tabs exactly as described in
`../it-leads-run/references/sheet-layout.md`: Leads, Watchlist, Config and
Run log, with headers, dropdowns, wrapping and widths. Fill Config with the
answers from step 2 and the defaults for everything else. Add any watchlist
accounts the user gave.

Tell the user in one sentence that the sheet is private to them unless they
share it.

## Step 4: Schedule the weekly run

Create one recurring scheduled task with the session's scheduling tool:

- **Name:** `IT leads (weekly)`
- **When:** the day and time from step 2, in the user's time zone. If the time
  is on the hour or half hour, move it a few minutes earlier.
- **Needs the user's computer:** no. The run is web research only.
- **Prompt:** the text below, with the sheet URL filled in.

```
Run the weekly IT lead research for this lead sheet: <SHEET URL>

Use the it-leads-run skill from the it-lead-agent plugin and follow it
exactly, including its hard rules: research only, never send or post anything,
never open LinkedIn or Sales Navigator, every lead needs a source that was
read in this run, and never change existing rows or the Status and My notes
columns.

If the it-leads-run skill is not available in this session, do not
improvise: stop and report that the plugin needs to be installed or enabled.
```

After creating it, say in one sentence which approval setting the task got. If
its runs will stop to ask for approval, mention that the user can switch the
task to automatic approval in its settings.

If no scheduling tool is available, say so plainly and tell the user they can
run `it-leads-run` by hand each week instead.

## Step 5: Offer a first run

Offer to run `it-leads-run` now so the sheet is not empty. If the user
agrees, run it.

## Step 6: Hand over

End with a short summary:

- where the sheet is and when the run happens;
- the weekly routine: read new rows, look up the person in Sales Navigator
  with the search recipe, send the note by hand, set Status, and write a
  reason in My notes when a lead is not a fit;
- that editing the Config tab changes the next run, and adding companies to
  Watchlist gets them re-checked;
- that `it-leads-brief` gives a short brief on one company before a call.

## Changing an existing setup

- Territory, plays, language, services, exclusions: edit the Config tab.
- Day or time: update the existing scheduled task; do not create a new one.
- Stopping: pause or delete the scheduled task. The sheet stays.
