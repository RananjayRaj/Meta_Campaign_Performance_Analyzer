# Meta Ads Performance Analyzer — SANITIZED n8n Workflow

This repository contains a sanitized export of the **Meta Ads Performance Analyzer** n8n workflow.
All API keys, email addresses, Google Sheet IDs, webhook IDs, and credential IDs have been replaced with placeholders.

**Files:**
- `workflows/meta-ads-performance-analyzer.sanitized.json` — sanitized n8n workflow (importable)
- `.env.example` — example environment variables with placeholders
- `README.md` — this file

## Quick start

1. Clone the repo and open your n8n instance.
2. Import the workflow: **Import → From File** → `workflows/meta-ads-performance-analyzer.sanitized.json`.
3. Create credentials in n8n (do NOT paste secrets into code nodes):
   - Google Sheets OAuth2
   - Anthropic (or your LLM provider) API credential
   - Gmail OAuth2 (for sending email reports)
   - Any scraping provider API key (if applicable)
4. Attach credentials via the n8n UI to the corresponding nodes:
   - `Save to Sheets` / `Export to Sheets1` → attach Google Sheets credential
   - `AI Analysis` → attach Anthropic/LLM credential
   - `Send Email Report1` → attach Gmail credential
5. Replace placeholders in node parameters **within the n8n UI** (recommended) or in the JSON before import:
   - `REPLACE_GOOGLE_SHEET_ID` — spreadsheet ID to write results
   - `REPLACE_NOTIFY_EMAIL` — recipient email for reports
   - `REPLACE_FIRECRAWL_API_KEY` — scraping API key if used
6. Activate the workflow triggers:
   - `Daily Analysis Trigger1` is a schedule trigger — ensure it's enabled to run on schedule.

## Security notes

- **Never** commit real API keys, client secrets, or credential files to a public repo.
- Prefer attaching credentials through n8n’s credential manager rather than editing exported JSON.
- If a secret was committed accidentally, **revoke/rotate** it immediately.

## Troubleshooting

- Import errors: if n8n complains about invalid JSON, make sure the file encoding is UTF-8 and there are no extra characters.
- Google Sheets write errors: ensure the Google Sheets credential has edit permission to the target spreadsheet.
- Gmail errors: ensure the Gmail OAuth credential is valid and not restricted by Google security policies.
