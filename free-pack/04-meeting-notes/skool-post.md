# Agent #4: Meeting Notes to Action Items Agent (n8n)

**What it does**
Paste a call transcript into a simple form. The agent sends you:
- A short summary of the call
- The decisions that were made
- An action item table with owners and due dates (only ones actually said on the call; anything unclear is marked "Unassigned" or "Not set")
- Open questions that still need an answer

It also writes a follow-up email to the attendees and saves it as a **Gmail draft**. Nothing is sent until you read it and hit send.

Works with transcripts from Zoom, Google Meet, Fathom, Otter, Fireflies, or anything else that gives you text.

**What you need**
- n8n (Cloud or self-hosted)
- A Gmail credential in n8n
- An Anthropic (Claude) API key added as a credential in n8n

**How to import**
1. Download the JSON file attached to this post.
2. In n8n, create a new workflow, open the **...** menu (top right), and choose **Import from File**. Pick the JSON. (You can also copy the file contents and paste them straight onto the canvas.)
3. Open the **Claude** node and select your Anthropic credential.
4. Open **Email Me the Notes** and **Draft the Follow-up** and select your Gmail credential.

**What to fill in**
Open **Config: Your Business** and replace every value that starts with "FILL IN":
- `your_name`, `your_email` (where the notes get sent), `business_name`
- `what_you_do` and `ideal_customer` (one or two sentences each, so the follow-up sounds like you)
- `tone_of_voice` (the default is fine to start)
- `email_signature` (how you sign off)

Optional, in **Config: Agent Settings**:
- `max_summary_bullets` (default 5)
- `follow_up_goal` (what the follow-up email should do)
- `include_open_questions` (true/false)

**How to use it**
1. Click **Publish** (called **Activate** in older n8n versions).
2. Open the **Paste a Meeting Transcript** node and copy the **Production URL**. Bookmark it.
3. After a call, open the form, add the meeting title and attendee emails (comma separated), paste the transcript, and submit.
4. Check your inbox for the notes and your Gmail drafts for the follow-up.

If you leave attendee emails blank, the follow-up draft is addressed to you.

**Make it yours**
Easy first change: rewrite `follow_up_goal` for your kind of calls (sales call, client check-in, internal standup).

Walkthrough video below shows the full build, node by node.
