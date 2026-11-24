# Compliance and limits

This page records the rules the agent is built around and the points that
the company still needs to confirm. It is not legal advice.

## Rules built into the agent

| Rule | Why |
|---|---|
| Never opens, reads or automates LinkedIn or Sales Navigator | LinkedIn's User Agreement prohibits automated access; accounts get restricted |
| Never sends messages, emails or connection requests | A person decides on and sends every contact |
| LinkedIn notes only, no cold email drafts | German UWG §7 restricts unsolicited advertising by electronic mail without prior consent |
| Every lead has a source that was read in the run | Leads must be checkable |
| Names a person only when a public source names them in a business role | Data minimisation |
| Never guesses emails or phone numbers | Accuracy and data protection |
| No outreach to public bodies outside the tender process | Procurement rules |
| Never edits the salesperson's Status or My notes | Their record of contact stays theirs |

## Personal data

- The sheet holds business information: company names, events, job titles,
  and occasionally the name and role of a person quoted in a press release.
- It holds no private contact details.
- Each sheet is private to its owner unless they share it.
- If a contact asks not to be approached, add their company to **Excluded
  companies** in the Config tab so it is not listed again.
- Before wider roll-out, the company's data protection contact should confirm
  that this fits the company's GDPR records and its rules on prospect data.

## To confirm with the company before roll-out

1. **Service list.** The drafts may only offer services in the Config tab's
   **Services to offer**. The default list is taken from the company's public
   website and has not been confirmed. Third-party maintenance is under
   **Services not to offer** until the company confirms whether it still sells
   it under its own name.
2. **Approval.** This is a pilot built outside the company. Outreach in the
   company's name is for its employees only.
3. **Claude plan and data rules.** Whether sales staff may use Claude for
   prospect research, and on which plan.
4. **Existing customers and competitors.** A list to put under **Excluded
   companies** so they are not approached as cold leads.
5. **Messaging.** Whether the example notes in
   `skills/it-leads-run/references/outreach.md` match how the company wants to
   be described.

## Known limits

- The agent infers that an event frees up or requires hardware; sources rarely
  say so directly.
- Search coverage varies between runs.
- Publication dates on some pages are missing; such rows say the date is
  estimated.
- The optional alert-email feature needs an email connector and reads
  notification emails; it is off by default.
