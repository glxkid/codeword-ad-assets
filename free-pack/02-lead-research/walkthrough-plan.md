# Walkthrough video plan: Agent #2, Lead Research

Target length: 10 to 12 minutes. Screen recording of n8n with face cam in the corner.

**Before recording**
- n8n with Gmail and Anthropic credentials connected.
- A list of 3 public companies you are comfortable showing on screen: one well-known company, one small local business, and one with a name that is also a common word (to show unrelated news being skipped).

| Time | On screen | What to say |
|---|---|---|
| 0:00 | The finished briefs email | "You paste a list of companies, and this agent researches each one and writes you a brief with a personalized opener." |
| 0:45 | Whole canvas | Tour: form, two config nodes, Split Leads, Fetch Website, Fetch News, Claude, Format, one email. |
| 1:45 | Import from File, connect credentials | Same as the other agents. |
| 2:30 | Config: Your Business | Fill in live. Stress that `what_you_do` drives the "fit" section. |
| 3:15 | Config: Agent Settings | Show max leads, news count, region, opener style. |
| 4:00 | Split Leads | Explain the "Company / website / person" format, and that blank lines are ignored. |
| 4:45 | Fetch Website and Clean Website Text | Run one lead and show the cleaned text. "This is everything Claude gets to read. No guessing." |
| 5:45 | Fetch News and Parse News | Show the Google News results. Point out an unrelated headline in the raw list. |
| 6:45 | Write Research Brief prompt | Show the rules: only use the provided text, skip headlines about other companies, say "Not found" when missing. Explain why this matters for outreach: a made-up fact in a first email kills trust. |
| 8:00 | Run all 3 leads | Submit the form with the production URL. |
| 9:00 | The briefs email | Walk through each brief. Show the local business with no news, and the unrelated headline being dropped. |
| 10:30 | Wrap | "Change one thing": rewrite `opener_style`. Mention it pairs with Agent #3. Point to the community. |

**Avoid saying**
- That it finds leads for you or books meetings. It researches leads you give it.
- Anything about reply rates, meetings, or revenue.
