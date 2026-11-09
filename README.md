# Reddit B2B Buying Intent & Competitor Mention Monitor

[![Run on Apify Store](https://img.shields.io/badge/Apify_Store-Run_Actor-00C853?style=for-the-badge&logo=apify)](https://apify.com/willowy_catamaran_fco/reddit-posts-b2b-scraper)
[![MCP Compatible](https://img.shields.io/badge/MCP-AI_Agent_Ready-7C3AED?style=for-the-badge)](https://apify.com/willowy_catamaran_fco/reddit-posts-b2b-scraper/api)
[![n8n & Clay Ready](https://img.shields.io/badge/Integrations-n8n_%7C_Clay_%7C_Make-FF6D5A?style=for-the-badge)](https://apify.com/willowy_catamaran_fco/reddit-posts-b2b-scraper)

Monitor Reddit discussions in real time for high-intent B2B buying signals ('looking for', 'alternative to', 'recommend', 'pricing', 'vs') with flat JSON output.

---

## Why Growth Teams & AI Agents Use This Actor
- **Flat, Pre-Validated JSON Output:** Zero nested arrays - maps directly into **Clay.com columns**, **n8n HTTP Request nodes**, **Make.com**, **HubSpot**, and **Airtable**.
- **High-Concurrency Async Engine:** Powered by concurrent worker pools and TLS browser impersonation (`curl_cffi`) with low 256MB-512MB RAM footprint.
- **MCP & Autonomous Agent Ready:** Runs under `LIMITED_PERMISSIONS` with predictable Pay-Per-Event pricing so Claude, Cursor, LangChain, and CrewAI agents can call it autonomously.

---

## Quick Start: 1-Click API Call (n8n / Clay / cURL)

Use the synchronous endpoint below in **Clay (HTTP API enrichment)** or **n8n (HTTP Request node)** to run the extraction and receive the JSON array in a single request:

```bash
curl -X POST "https://api.apify.com/v2/acts/willowy_catamaran_fco~reddit-posts-b2b-scraper/run-sync-get-dataset-items?token=YOUR_APIFY_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{
  "query": "AI automation workflow",
  "sort": "relevance",
  "maxItems": 50
}'
```

---

## Sample Input
```json
{
  "query": "AI automation workflow",
  "sort": "relevance",
  "maxItems": 50
}
```

## Real Output Sample
```json
{
  "subreddit": "r/AI_Agents",
  "author": "IndicationTypical972",
  "title": "What is something that you have successfully automated with an AI Agent?",
  "hasBuyingIntent": true,
  "buyingSignalsCsv": "workflow",
  "postUrl": "https://www.reddit.com/r/AI_Agents/comments/1xh0rib/"
}
```

---

## Connect to Claude Desktop / Cursor via Apify MCP
Add this Actor to your AI agent toolset using the official Apify MCP Server:
```json
{
  "mcpServers": {
    "apify-b2b-tools": {
      "command": "npx",
      "args": [
        "-y",
        "@apify/actors-mcp-server",
        "--actors",
        "willowy_catamaran_fco/reddit-posts-b2b-scraper"
      ],
      "env": {
        "APIFY_TOKEN": "YOUR_APIFY_TOKEN"
      }
    }
  }
}
```

## Keywords & Integrations
`reddit-scraper, social-listening, b2b-buying-signals, lead-generation, ai-agents, n8n-automation, apify-actor`
