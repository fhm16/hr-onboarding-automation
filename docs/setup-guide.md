# Detailed Configuration Guide

1. **Google Sheets Trigger:** Connect Google Sheets OAuth2 credential and select `Trigger On: Row Added`.
2. **Edit Fields (Set Node):** Generates `corporate_email` (`firstname.lastname@yourcompany.com`) and sets `temp_password`.
3. **Gmail Node:** Sends personalized welcome email with credentials to the employee's personal email.
4. **Slack Nodes:**
   - **Node 1 (`#general`):** Posts company-wide welcome announcement.
   - **Node 2 (Dynamic Department):** Uses expression `{{ $json['Department '].toLowerCase().trim() }}` to route to `#sales`, `#marketing`, or `#engineering`. Ensure the Slack App has `chat:write` and `chat:write.public` scopes.
5. **Notion Node:** Creates a structured onboarding page with dynamic employee details and a 4-step first-week checklist.