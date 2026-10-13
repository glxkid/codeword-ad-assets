# Walkthrough video plan: Agent #3, Outreach and Follow-up

Target length: 12 to 14 minutes. Screen recording of n8n with face cam in the corner. This is the most complex agent in the pack, so take the "how it remembers" part slowly.

**Before recording**
- n8n with Gmail and Anthropic credentials connected.
- A second email address you own to play the lead (never use a real prospect on camera).
- To show a follow-up without waiting 3 days, set `follow_up_after_days` to 0 for the recording, then set it back at the end on camera.

| Time | On screen | What to say |
|---|---|---|
| 0:00 | Gmail drafts: a first email and a follow-up in the same thread | "This agent writes your outreach and your follow-ups, and stops the moment someone replies. Everything is a draft, so you stay in control." |
| 1:00 | Whole canvas | Two triggers: the form (new lead) and every morning (follow-ups). Both go through the same config, then split. |
| 2:00 | Import from File, connect credentials | Two Claude nodes and three Gmail nodes. |
| 3:00 | Config: Your Business and Config: Agent Settings | Fill in live. Explain `outreach_goal`, `follow_up_after_days`, `max_follow_ups`. |
| 4:15 | Top path: Write First Email | Show the rules: short, plain text, no fake urgency, no claims about other clients' results. |
| 5:15 | Save Lead | "This is the agent's memory. It saves the lead inside the workflow." Explain why you must publish and use the production URL. |
| 6:00 | Publish, add the test lead | Submit the form. Open Gmail drafts, edit one line, send it to your second address. |
| 7:15 | Bottom path: Load Active Leads and Check Gmail | Explain the daily check: one Gmail search finds what you sent and whether they replied. |
| 8:30 | Pick Leads to Follow Up | Explain the rules in plain words: replied means stop, not sent yet means wait, draft waiting means wait, limit hit means stop. Don't read the code. |
| 9:45 | Run the daily check manually | Show the follow-up draft landing in the same thread. (Test this before recording. If a manual run doesn't see the saved lead, temporarily set **Every Morning** to run every minute and let the published workflow run it.) |
| 10:45 | Reply from the second address, run the check again | Show that no new follow-up is created. This is the key moment. |
| 11:45 | Wrap | Set `follow_up_after_days` back to 3. "Change one thing": the outreach goal. Mention pairing with Agent #2. Point to the community. |

**Avoid saying**
- Anything about reply rates, booked calls, or revenue.
- That it sends emails for you. It writes drafts; you send them.

**Do mention**
- Cold outreach rules differ by country. Follow the rules where you and your leads are.
