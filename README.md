# IT Lead Agent

A Claude add-on that finds new sales leads every week for a company that
buys, refurbishes and resells enterprise IT hardware.

> An independent student proposal by Ibrahim Kalil. It is not affiliated
> with any company.

## What it does

Every week it reads public business news from Germany and looks for
companies that are likely to:

- **sell** old IT hardware (for example, they are moving to the cloud),
- **buy** hardware or GPUs (for example, they are building an AI data centre),
- **partner** with the company (IT resellers that are growing).

Each lead goes into a spreadsheet with:

- what happened, and the link to the news,
- why it is a good fit,
- which job title to look for in LinkedIn Sales Navigator,
- a short LinkedIn message, ready to send.

**A person still sends every message.** The agent never contacts anyone and
never logs in to LinkedIn.

## How it works

```mermaid
flowchart LR
    A[Reads news<br/>every week] --> B[Picks companies<br/>with a reason to buy or sell]
    B --> C[Writes leads<br/>into a sheet]
    C --> D[You find the person<br/>in Sales Navigator<br/>and send the message]
```

## Sources it uses

All free and public.

| Source | Example from the test |
|---|---|
| IT trade news | [ChannelPartner](https://www.channelpartner.de): Connexta buys another IT reseller |
| IT trade news | [CIO.de](https://www.cio.de): HARTING moves its SAP system to the cloud |
| Tech news | [Borncity](https://borncity.com): KIT replaces its supercomputer |
| Company press releases | Polarise launches a new AI cloud |
| Your own watchlist | Companies you save in Sales Navigator |

It also searches DataCenter-Insider, IT-Business, Computerwoche, it-daily, SAP
News and public tender portals (TED, DTVP). Tenders did not work well in the
test, because those sites block automated reading.

### Do you know better sources?

You know this market better than I do. I would love your input:

1. Which **magazines, newsletters or websites** do you read for industry news?
2. What usually **happens before a deal**? For example: an office move, a
   leasing contract ending, a merger.
3. Do you already use any **tender alerts or lead databases**?
4. Could I see a list of **typical customers or partners**? The agent could
   then look for similar companies.

Please reply to me directly or
[open an issue](https://github.com/ibk-1/it-lead-agent/issues) here.

## First test (14 November 2026)

It found 4 leads in Germany:

| Company | Lead type | Why |
|---|---|---|
| Connexta | Partner | Bought its fifth IT reseller this year |
| Polarise | Buyer | Launched a new AI cloud |
| HARTING | Seller | Moving its SAP system to the cloud |
| KIT Karlsruhe | Seller | New supercomputer replaces the old one (public body: tender only) |

[See the full test](docs/TEST-RUN.md)

## Try it

You need a paid Claude plan. It does not work in ChatGPT.

1. In Claude, go to **Customize → Plugins → Add marketplace**.
2. Enter `ibk-1/it-lead-agent` and click **Install**.
3. Open a new chat and type `/it-leads-setup`.
4. Answer four short questions, or say "use the defaults".

[Step-by-step guide](docs/GETTING-STARTED.md)

## Good to know

- It only finds what is published online.
- It suggests a job title, not a person. You find the person in Sales
  Navigator.
- It writes LinkedIn messages only, no cold emails (German law restricts
  them).
- The company would need to confirm which services the messages may offer.

## More

- [How I built it](docs/HOW-I-BUILT-IT.md): the story behind it
- [Step-by-step guide](docs/GETTING-STARTED.md): setup and weekly use
- Technical details: [how it works](docs/HOW-IT-WORKS.md),
  [rules and data protection](docs/COMPLIANCE.md),
  [test report](docs/TEST-RUN.md)
