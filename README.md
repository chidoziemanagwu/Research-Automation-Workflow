# n8n Research Automation Workflow

An n8n workflow to automate academic literature review, AI analysis, and research report generation.

## 🚀 Features

- Multi-source data collection (Semantic Scholar, OpenAlex, Crossref, arXiv, PubMed)
- AI-powered content extraction and synthesis using **Groq’s Llama 3.3 (70B)**
- Smart scoring for relevance and quality
- Google Sheets integration for persistent data storage
- Automated HTML email reports

## ⚙️ Workflow Overview
Manual Trigger → Configuration → 5 Parallel API Calls →
Merge → Normalize → AI Extract → Score → Filter →
Google Sheets + AI Synthesis → Format → Email


## 🧠 Prerequisites

- n8n instance (self-hosted or cloud)
- **Groq API key**
- **Google account** (for Gmail + Google Sheets)
- Basic knowledge of n8n nodes and credentials

## 🧩 Customization

| Parameter | Location | Example | Description |
|------------|-----------|----------|--------------|
| `keywords` | Set Search Config | `"circular economy battery recycling"` | Research topic keywords |
| `min_year` | Set Search Config | `"2020"` | Minimum publication year |
| `max_results` | Set Search Config | `"10"` | Number of results per source |
| `relevance_threshold` | Set Search Config | `"15"` | Minimum score for paper inclusion |
| Recipient Email | Email Synthesis Report | `"you@example.com"` | Change default email destination |

## 🪄 Example Use Cases

- Automated literature reviews for dissertations or proposals  
- Academic or market trend scouting  
- Generating sustainability research summaries  
- Identifying gaps for future research

## 🧭 Repository Structure

.
├── README.md → Overview and usage guide
├── SETUP.md → Step-by-step installation & configuration
└── workflow.json → The actual n8n workflow


## 🧰 Troubleshooting

- **429 Too Many Requests** → Increase the delay in “Rate Limit Delay” nodes or reduce `max_results`.
- **No Papers Processed** → Lower `relevance_threshold` or broaden keywords.
- **Email Not Delivered** → Check Gmail credentials / OAuth2 setup.
- **AI Timeout** → Reduce number of papers or check Groq API quota.

## 📄 License

MIT License — Feel free to modify and reuse.

---

**Built with ❤️ for researchers — powered by n8n + Groq AI**
