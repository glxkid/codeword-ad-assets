# Agent #5: Review Responder Agent (n8n)

**What it does**
Give it a customer review (Google, Yelp, Trustpilot, Facebook, anywhere) and it emails you a reply draft that you can copy and post.

Every review gets one of two labels in the subject line:
- **[READY TO POST]**: a positive review with a friendly, specific reply ready to use.
- **[NEEDS YOU]**: the review is negative, low-rated, or mentions something sensitive (refund, sick, unsafe, lawyer, and so on). You still get a suggested reply, but the email tells you to handle it personally.

The agent never posts anything publicly and never offers refunds, discounts, or admits fault. You stay in control of what goes out.

**What you need**
- n8n (Cloud or self-hosted)
- A Gmail credential in n8n
- An Anthropic (Claude) API key added as a credential in n8n

**How to import**
1. Download the JSON file attached to this post.
2. In n8n, create a new workflow, open the **...** menu (top right), and choose **Import from File**. Pick the JSON.
3. Open the **Claude** node and select your Anthropic credential.
4. Open **Email Me the Reply** and select your Gmail credential.

**What to fill in**
Open **Config: Your Business** and replace every value that starts with "FILL IN":
- `your_name`, `your_email` (where reply drafts get sent), `business_name`
- `what_you_do` and `ideal_customer`
- `tone_of_voice` and `email_signature`

Then open **Config: Agent Settings**:
- `contact_for_issues`: where unhappy customers can reach you (email or phone). The agent uses this in replies to negative reviews.
- `reply_sign_off`: how replies are signed, e.g. "Thanks again, the team at Sunrise Bakery".
- `flag_at_or_below_stars`: reviews at or below this rating are flagged (default 3).
- `always_flag_words`: words that always flag a review for you, no matter the rating.
- `reply_length` (default 2 to 4 sentences).

**How to use it**
1. Click **Publish** (called **Activate** in older n8n versions).
2. Open the **Paste a Review** node, copy the **Production URL**, and bookmark it.
3. When a new review comes in, paste it into the form with the platform, name, and star rating.
4. Check your inbox, read the reply, and post it on the platform yourself.

**Optional: run it from review emails**
If your review platform emails you when a new review comes in, you can skip the form:
1. Right-click **New Review Email (optional)** and choose **Activate** (it is turned off by default).
2. Select your Gmail credential.
3. Edit the search in the node so it matches the emails you get, for example `from:businessprofile-noreply@google.com`.

Some platforms only include part of the review in the email. If the reply looks off, paste the full review into the form instead.

**Make it yours**
Easy first change: add words to `always_flag_words` that matter in your industry (for a dentist: "pain", "billing"; for a restaurant: "allergy").

Walkthrough video below shows the full build, node by node.
