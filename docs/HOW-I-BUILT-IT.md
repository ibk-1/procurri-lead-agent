# How I built it

*Ibrahim Kalil, November 2026*

## The question

How could a company that buys and resells IT hardware find businesses that
want to **sell** or **buy** it, ideally with LinkedIn Sales Navigator?

## What I found out

**Sales Navigator cannot be automated.** It has no export, and bots break
LinkedIn's rules. But it is great for finding the right person.

**Timing matters most.** A company becomes a lead when something happens:
a cloud move, a new data centre, a merger. That news is public.

So I split the work:

| The agent | The salesperson |
|---|---|
| Finds the company and the news | Finds the person in Sales Navigator |
| Explains why it is a good fit | Decides if it is worth it |
| Writes a short LinkedIn message | Sends it |

## Why a Claude add-on

I compared two options:

- **Custom software** with a server and database: weeks of work and upkeep.
- **A Claude add-on:** written in plain text, built in a day, installed in
  two minutes, and nothing to maintain.

The add-on is the faster way to test the real question: do these leads get
replies?

## The test

One run on 14 November found 4 leads in Germany: one partner, one buyer and
two sellers. Every lead had a working news link, and every message was under
300 characters.

What I learned:

- **Partner and buyer leads were strongest.** The news was clear and recent.
- **Seller leads were weaker.** Articles rarely say what happens to old
  hardware, so the messages ask instead of assuming.
- **Tender websites block automated reading.** Their own email alerts would
  be the better route.

## What I left out on purpose

- **Bots that get around website blocks.** If a site says no, the agent
  respects it.
- **Paid lead databases.** They list companies, but not *why now*. They can
  be added later if needed.
- **Cold emails.** German law restricts them, so the agent writes LinkedIn
  messages only.

## Suggested next step

A four-week pilot with one salesperson. It is a success if:

- each week has at least 3 leads worth contacting, and
- at least one lead turns into a reply or meeting.

Before that, the company would need to confirm which services the messages may
offer, and which companies to leave out (for example existing customers).

## How it was made

I designed it with Claude, Anthropic's AI assistant. Claude helped with
research, wrote the instruction files and ran the test. I made the decisions.

---

[Try it yourself](GETTING-STARTED.md) · [Back to the overview](../README.md)
