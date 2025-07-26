# n8n Workflows

This repository contains my collection of n8n workflow automations.

## Structure

- `workflows/` - Contains exported n8n workflow files (.json)

## Usage

1. Import workflow files into your n8n instance
2. Configure any required credentials and connections
3. Activate workflows as needed

## Workflows

### AI Organizational Summary Bot
**File:** `ai-organizational-summary.json`

An intelligent workflow that provides personalized organizational summaries on-demand via WhatsApp or Slack prompts.

**Features:**
- Fetches data from Notion, Slack, and Email
- Uses AI to analyze and summarize information  
- Responds to natural language requests
- Provides personalized todo items and action items
- Supports time-based queries (today, yesterday, this week)

**Setup Requirements:**
1. OpenAI API key for AI analysis
2. Notion integration with database access
3. Slack integration with channel access  
4. Email IMAP credentials (Gmail supported)
5. Environment variables:
   - `NOTION_DATABASE_ID`
   - `SLACK_CHANNEL_ID` 
   - `EMAIL_ADDRESS`
   - `EMAIL_PASSWORD`

**Usage:**
Send webhook POST requests to `/org-summary` endpoint with:
```json
{
  "message": "give me a summary of what happened yesterday",
  "user_id": "user123",
  "platform": "slack"
}
```

**Example Prompts:**
- "Give me a summary of what happened in the organization yesterday"
- "What are my todo items from this week?"
- "Show me Notion updates from today"
- "Slack only summary for yesterday"
