# Step-by-step guide

About 15 minutes. You need a paid Claude plan. It does not work in ChatGPT.

## 1. Install

1. Open Claude.
2. Go to **Customize → Plugins → Add marketplace**.
3. Enter `ibk-1/it-lead-agent`.
4. Click **Install**.

Nothing runs yet.

*Didn't work?* Download the `.plugin` file from this repository's
**Releases** page (or ask me for it), then upload it under
**Customize → Plugins**.

## 2. Set it up

Open a **new chat** and type:

```
/it-leads-setup
```

Claude asks four questions:

| Question | Default |
|---|---|
| Which region? | Germany |
| Which kinds of leads? | All four: sellers, buyers, partners, tenders |
| Message language? | German |
| When should it run each week? | Monday morning |

Then two optional ones: companies to **leave out** (for example existing
customers) and companies to **keep an eye on**.

You can answer in one line, for example:

> Germany, everything, German, Tuesday 8:40.

Or just say **"use the defaults"**.

## 3. What you get

- **A lead sheet**, private to you.
- **A weekly run** at the time you chose. Your computer can be off.

Claude then offers a first run. Say **yes**. After a few minutes your first
leads appear.

**One thing to check:** if Claude says the weekly run "asks for approval",
open the task's settings and turn on **automatic approval**. Otherwise it
waits for you every week.

## 4. Every week (about 30 minutes)

1. Open your lead sheet.
2. Read the new leads and open the news links.
3. Find the person in Sales Navigator. Each lead has a ready search, for
   example: *Company: Connexta · Title: Head of Procurement · Germany*.
4. Send the LinkedIn message from the sheet (edit it if you like).
5. Set the **Status**: Contacted, Replied, Meeting, Not a fit or Later.
   If it is not a fit, add a short reason.

The agent learns from your statuses and improves the next week.

## Other commands

- `/it-leads-run` runs it now, without waiting for the weekly run.
- `/it-leads-brief Connexta` gives a short brief before a call.

## Change or stop

- **Settings:** edit the **Config** tab in your sheet.
- **Pause:** pause the weekly task in Claude.
- **Remove:** delete the task, then remove the plugin under
  **Customize → Plugins**.

## Problems?

| Problem | Fix |
|---|---|
| `/it-leads-setup` not found | Open a new chat. Check the plugin is on under **Customize → Plugins**. |
| The weekly run waits | Turn on automatic approval for the task. |
| No new leads | Normal in a quiet week. Try more regions in **Config**. |
