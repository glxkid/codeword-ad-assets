# Walkthrough video plan: Agent #5, Review Responder

Target length: 8 to 10 minutes. Screen recording of n8n with face cam in the corner.

**Before recording**
- n8n with Gmail and Anthropic credentials connected.
- Three made-up reviews for a fake business (for example "Sunrise Bakery"): one 5-star, one 4-star that mentions getting sick, one 2-star about slow service. Do not use real customer reviews or names.

| Time | On screen | What to say |
|---|---|---|
| 0:00 | Two finished emails side by side: [READY TO POST] and [NEEDS YOU] | "This agent drafts replies to your reviews and tells you which ones you should handle yourself." |
| 0:45 | Whole canvas | Tour: form (and the optional email trigger), Normalize, two config nodes, Claude, Decide and Format, Gmail. |
| 1:30 | Import from File, connect credentials | Same as the other agents. |
| 2:15 | Config: Your Business | Fill in live. |
| 3:00 | Config: Agent Settings | Explain `contact_for_issues`, the star threshold, and `always_flag_words`. "This is your safety net. Even if Claude thinks a review is fine, these words always send it to you." |
| 4:00 | Draft Reply prompt | Point out the rules: no refunds, no admitting fault, no private details, invite unhappy customers to talk privately. |
| 5:00 | Decide and Format | Explain the three checks (Claude's judgment, star rating, flag words) without reading code. |
| 5:45 | Publish, run the 5-star review | Show the [READY TO POST] email. |
| 6:30 | Run the 4-star "got sick" review | Show it gets flagged even though it is 4 stars. This is the key moment. |
| 7:15 | Run the 2-star review | Show the reply invites them to get in touch privately. |
| 8:00 | Optional email trigger | Show how to enable it and edit the search. Mention some platforms only send part of the review. |
| 8:45 | Wrap | "Change one thing": add flag words for your industry. Point to the community for questions. |

**Avoid saying**
- Anything about ratings going up, more customers, or revenue.
- That it can post replies automatically. It can't, by design.
