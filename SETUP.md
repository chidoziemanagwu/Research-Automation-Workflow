# Setup Guide – n8n Research Automation Workflow

Follow this guide to import and configure the workflow in n8n.

---

## 1️⃣ Import the Workflow

1. Download the `workflow.json` file.
2. Open n8n.
3. Click **Workflows → New Workflow**.
4. In the top-right menu (⋮), choose **Import from File**.
5. Upload `workflow.json`.

---

## 2️⃣ Configure Credentials

### a. Groq API

1. Get your API key from [Groq Cloud](https://console.groq.com/keys).
2. In n8n → **Credentials → New Credential → OpenAI API**.
3. **Base URL:** `https://api.groq.com/openai/v1`  
   **API Key:** your Groq key.
4. Save and assign this credential to:
   - **Extract Paper Sections (Groq AI)**
   - **Generate Thematic Synthesis (Groq AI)**

### b. Google Sheets + Gmail

1. In n8n → **Credentials → New Credential → Google**.
2. Choose **OAuth2** authentication.
3. Connect your Google account and authorize both **Sheets** and **Gmail** scopes.
4. Save as e.g., `Google Account`.
5. Assign this credential to:
   - **Save to Google Sheets**
   - **Email Synthesis Report**

---

## 3️⃣ Edit Workflow Parameters

### Node: Set Search Config
| Key | Example | Description |
|-----|----------|-------------|
| `keywords` | `"circular economy battery recycling"` | Research topic |
| `min_year` | `"2020"` | Minimum publication year |
| `max_results` | `"10"` | Papers per source |
| `relevance_threshold` | `"15"` | Filtering threshold |

### Node: Calculate Quality & Relevance Scores
Edit the `keywords` array in the code section to reflect your topic focus.

### Node: Email Synthesis Report
Change the “To” field to your target email address.

---

## 4️⃣ Test It

1. Click the **Manual Trigger** node.
2. Click **Execute Workflow**.
3. Watch nodes execute → check:
   - Google Sheet for paper data
   - Inbox for AI-generated synthesis report

---

## 5️⃣ Common Fixes

| Issue | Possible Cause | Fix |
|-------|----------------|-----|
| 429 errors | API rate limits | Increase delay nodes (3–5 seconds) |
| 0 papers found | Filters too strict | Lower threshold or broaden keywords |
| No email | Gmail OAuth misconfigured | Reconnect Google credentials |
| AI errors | Groq key invalid or quota reached | Refresh key or retry later |

---

### ✅ Done!  
Your n8n research automation pipeline is ready to analyze and synthesize literature with one click.  

**Happy researching!**
