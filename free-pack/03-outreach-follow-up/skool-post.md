# Agent #3: Outreach and Follow-up Agent (n8n)

**What it does**
Add a lead through a simple form and the agent writes a first outreach email in your voice and saves it as a **Gmail draft**. You read it, edit it if you want, and send it yourself.

From then on it checks your Gmail every morning:
- **They replied?** It stops. No more follow-ups for that lead.
- **No reply, and enough days have passed since your last email?** It writes the next follow-up and saves it as a draft in the same email thread.
- **Hit your follow-up limit?** It stops. The last follow-up politely closes the loop.

Every email is a draft. Nothing is ever sent without you.

**What you need**
- n8n (Cloud or self-hosted)
- A Gmail credential in n8n (the same Gmail you send outreach from)
- An Anthropic (Claude) API key added as a credential in n8n

**How to import**
1. Download the JSON file attached to this post.
2. In n8n, create a new workflow, open the **...** menu (top right), and choose **Import from File**. Pick the JSON.
3. Open both Claude nodes (**Claude** and **Claude (follow-ups)**) and select your Anthropic credential.
4. Open the three Gmail nodes (**Draft First Email**, **Check Gmail for Sends and Replies**, **Draft Follow-up**) and select your Gmail credential.

**What to fill in**
Open **Config: Your Business** and replace every value that starts with "FILL IN":
- `your_name`, `your_email`, `business_name`
- `what_you_do` and `ideal_customer`: the emails are built from these, so be specific
- `tone_of_voice` and `email_signature`

Then open **Config: Agent Settings**:
- `outreach_goal`: what you want them to do, e.g. "Ask if they are open to a 15-minute call"
- `follow_up_after_days`: days to wait after your last email (default 3)
- `max_follow_ups`: follow-ups after the first email (default 3)
- `max_leads_checked_per_day` (default 40)

**How to use it**
1. Click **Publish** (called **Activate** in older n8n versions). This matters: the agent only remembers leads when it is published.
2. Open the **Add a Lead** node, copy the **Production URL** (not the test URL), and bookmark it.
3. Add a lead: name, email, company, and why you are reaching out. The more specific "Why them" is, the better the email. Tip: paste a brief from Agent #2 (Lead Research) here.
4. Open your Gmail drafts, review the email, and send it.
5. That's it. Follow-up drafts show up in your drafts folder on the right days. Review and send them the same way.

**Good to know**
- Follow-ups only start after you actually send the first email. An unsent draft just waits.
- The agent will not stack up drafts. If a follow-up draft is waiting for you, it won't write another.
- To stop following up with someone, delete their follow-up draft. The agent won't create another one for that lead.
- It runs every morning at 9:00 in your n8n timezone. Change it in the **Every Morning** node.

**Make it yours**
Easy first change: rewrite `outreach_goal` for your offer, and set `follow_up_after_days` to match how you like to follow up.

Walkthrough video below shows the full build, node by node.
