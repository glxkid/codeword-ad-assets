# Walkthrough video plan: Agent #4, Meeting Notes to Action Items

Target length: 8 to 10 minutes. Screen recording of n8n with face cam in the corner.

**Before recording**
- A clean n8n workspace with Gmail and Anthropic credentials already connected (blur the key if it is visible).
- A sample transcript of a fake call (no real client names). A 3 to 5 minute call is enough.
- Gmail open in a second tab, drafts folder empty.

| Time | On screen | What to say |
|---|---|---|
| 0:00 | Finished result: the notes email and the follow-up draft | "This agent turns any call transcript into notes, action items, and a follow-up draft. Here's what it gives you, then I'll show you how it's built." |
| 0:45 | n8n canvas, whole workflow | Quick tour: form, two config nodes, Claude, format, two Gmail nodes. "Eight nodes, no code you have to write." |
| 1:30 | Import from File | Show importing the JSON from the Skool post. Connect Anthropic and Gmail credentials. |
| 2:30 | Config: Your Business | Fill in each field live. Explain that `what_you_do` and `tone_of_voice` shape the follow-up email. |
| 3:30 | Config: Agent Settings | Show `follow_up_goal`. Change it once (for example to a client check-in) to show how it changes the output. |
| 4:15 | Extract Notes and Actions | Open the prompt. Point out the rules: only facts from the transcript, "Unassigned" when the owner is unclear, "Not set" when no due date was said. Explain why: you don't want made-up deadlines in a client email. |
| 5:30 | Format Notes (Code node) | Don't read the code. Explain what it does: turns Claude's answer into the email table, and picks the follow-up recipients. |
| 6:15 | Publish, open the form | Paste the sample transcript, submit. |
| 7:00 | Gmail inbox and drafts | Walk through the notes email and the draft. Edit one line of the draft to show it is yours to change before sending. |
| 8:00 | Back in n8n | "Change one thing to make it yours." Suggest: rewrite the follow-up goal, or change the summary length. Point to the community for questions. |

**Avoid saying**
- Anything about time saved, money made, or client results.
- That it "never makes mistakes". Say: "Always read the draft before you send it."
