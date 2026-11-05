# P.R.O. Apple Health MCP

Free hosted MCP server for Apple Health. Ask ChatGPT, Claude, Gemini, Grok, Perplexity, Cursor or Codex about your workouts, sleep, HRV and training load. No export.xml, no Mac and no terminal: your iPhone syncs the data, and you sign in with OAuth.

**Server address:** `https://mcp.proapp.uk`

It works with Apple Watch and any device that writes to Apple Health, such as Garmin, WHOOP and Oura.

## Connect

You need the free [P.R.O. iPhone app](https://proapp.uk/apple-health-mcp). The assistant opens a sign-in page, and you confirm with a one-time code from the app.

| Assistant | How to add it |
|---|---|
| ChatGPT | Install [P.R.O. from the ChatGPT plugin directory](https://chatgpt.com/plugins/plugin_asdk_app_6ad22f791530819196ed668dfdbf6909) |
| Claude | Connectors → Add custom connector → name P.R.O., URL `https://mcp.proapp.uk` |
| Claude Code | `claude mcp add --transport http pro https://mcp.proapp.uk` |
| Codex | `codex mcp add pro --url https://mcp.proapp.uk`, then `codex mcp login pro` |
| Cursor | Add `{ "mcpServers": { "pro": { "url": "https://mcp.proapp.uk" } } }` to `~/.cursor/mcp.json` |

Guides for every assistant, including Gemini, Grok, Perplexity, Manus and Cherry Studio: [proapp.uk/mcp-connect](https://proapp.uk/mcp-connect).

## What you can ask

- "How did I sleep this week compared with last week?"
- "Am I recovered enough for intervals today?"
- "Summarize my training load for the last month."
- "Show my last run with pace and heart rate."

The server has 15 tools covering your profile, goals, daily metrics, workouts, sleep, heart rate and HRV, training load and training plan, plus interactive cards in ChatGPT, Claude and Gemini. An assistant can suggest changes to your training plan, and nothing changes until you accept them in P.R.O.

## Your data

Health data stays on your device until you choose to send it to an AI assistant. You pick the categories it can read and can disconnect at any time in P.R.O. under Settings → MCP Connect.

P.R.O. provides fitness and wellness information, not medical advice.

## Details

- **Transport:** Streamable HTTP
- **Auth:** OAuth 2.1 with dynamic client registration and PKCE
- **Price:** the MCP connector is free
- **Links:** [Apple Health MCP guide](https://proapp.uk/apple-health-mcp) · [Privacy](https://proapp.uk/privacy) · [Terms](https://proapp.uk/terms)
- **Contact:** p.r.o.devel001@gmail.com

This repository holds the public MCP Registry metadata for P.R.O. The server itself is hosted.
