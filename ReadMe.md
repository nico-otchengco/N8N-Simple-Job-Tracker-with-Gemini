# AI Job Application Tracker (n8n)

A simple automated pipeline that logs job applications via curl command, 
enriches them with Gemini 2.5 flash, saves to Google Sheets, 
and sends email confirmations.

## Stack
- n8n (workflow automation)
- Gemini API (gemini-2.5-flash)
- Google Sheets API
- Gmail API

## Flow
Webhook (curl command) → AI Enrichment → Google Sheets → Email Notification

## How to Use
1. Import `workflow.json` into your n8n instance
2. Set up credentials (Gemini, Google)
3. Since im using self-hosted n8n only, run the following curl command in your terminal (replace the URL with your actual n8n Webhook URL):

curl -X POST http://localhost:5678/webhook-test/job-tracker ^
     -H "Content-Type: application/json" ^
     -d "{\"email\": \"example@email.com\", \"company\": \"Microsoft\", \"role\": \"Software Engineer\", \"status\": \"Applied\", \"notes\": \"Applied via LinkedIn\"}"