# Agent #2: Lead Research Agent (n8n)

**What it does**
Paste a list of companies (and the person you want to reach, if you know it). For each lead, the agent:
1. Reads the company's homepage
2. Pulls the latest Google News headlines about them
3. Has Claude write a short brief: what they do, recent news worth knowing, how your offer might fit, and a personalized first line for an outreach email

You get every brief in one email. Claude is told to use only what it found on the website and in the news. If it can't find something, it says so instead of making it up. Unrelated headlines (another company with a similar name) are skipped.

Nothing is sent to your leads. Pair it with Agent #3 (Outreach and Follow-up) when you are ready to reach out.

**What you need**
- n8n (Cloud or self-hosted)
- A Gmail credential in n8n
- An Anthropic (Claude) API key added as a credential in n8n

No other accounts or API keys. Website and news lookups use public pages.

**How to import**
1. Download the JSON file attached to this post.
2. In n8n, create a new workflow, open the **...** menu (top right), and choose **Import from File**. Pick the JSON.
3. Open the **Claude** node and select your Anthropic credential.
4. Open **Email Me the Briefs** and select your Gmail credential.

**What to fill in**
Open **Config: Your Business** and replace every value that starts with "FILL IN":
- `your_name`, `your_email` (where the briefs get sent), `business_name`
- `what_you_do`: this is what Claude uses to judge fit, so be specific
- `ideal_customer`, `tone_of_voice`, `email_signature`

Optional, in **Config: Agent Settings**:
- `max_leads_per_run` (default 20)
- `news_items_per_lead` (default 3)
- `news_region` (default US; use GB, CA, AU, etc.)
- `opener_style`: how the personalized first line should sound

**How to use it**
1. Click **Publish** (called **Activate** in older n8n versions).
2. Open the **Paste Your Leads** node, copy the **Production URL**, and bookmark it.
3. Paste your leads, one per line, in this format:
   `Company | website | person`
   The person is optional. Example:
   `Acme Plumbing | acmeplumbing.com | Dana Lee`
4. Optional: fill in "What are you offering them?" if this batch is for a specific offer.
5. Submit. The briefs land in your inbox a few minutes later.

**Good to know**
- Small local businesses often have no news coverage. The brief will say "Nothing relevant found", and the opener will be based on the website.
- Some websites block automated visits. When that happens, the brief notes that the site could not be read.
- Always check an opener against the source before you use it.

**Make it yours**
Easy first change: rewrite `opener_style` to match how you actually write (for example "one question about their business, no compliments").

Walkthrough video below shows the full build, node by node.
