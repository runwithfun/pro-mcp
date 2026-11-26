# P.R.O. Apple Health MCP Server

**Free, hosted Apple Health MCP.** Ask ChatGPT, Claude, Grok, Cursor or Codex about your real workouts, sleep, HRV and training load, and get answers built from your own numbers.

```
https://mcp.proapp.uk
```

Add that address to your assistant, confirm with a one-time code from the free P.R.O. iPhone app, and you're done. No `export.xml`, no Mac, no terminal. Your iPhone keeps the data fresh, and it works in the assistant apps on your phone too.

Works with Apple Watch and any device that writes to Apple Health: Garmin, WHOOP, Oura, Polar, COROS, Withings and more.

> **You:** Am I ready for intervals today?
>
> **Claude:** Yes, with one caution. HRV is 47 ms, in line with your 28-day average, and resting heart rate is 52 bpm. You slept 7 h 10 min. Your 7-day load is 18% above your 4-week average, so keep the intervals and cut the cool-down run short.
>
> <sub>Example with sample data.</sub>

<p>
  <img src="https://proapp.uk/img/mcp/claude/card-sleep-960.webp" width="32%" alt="Sleep card from P.R.O. in Claude">
  <img src="https://proapp.uk/img/mcp/claude/card-workout-960.webp" width="32%" alt="Workout card from P.R.O. in Claude">
  <img src="https://proapp.uk/img/mcp/chatgpt/card-plan-1412.webp" width="32%" alt="Training plan card from P.R.O. in ChatGPT">
</p>

## Why P.R.O.

- **Free.** The MCP server and the iPhone app cost nothing.
- **No export, no computer.** The iPhone app syncs Apple Health in the background. No files to re-export, no local server to keep running.
- **Works on your phone.** Use it in the ChatGPT, Claude and Grok iPhone apps, not only on a desktop.
- **You choose what it reads.** Turn categories on or off (workouts, sleep, heart rate and HRV, routes and more) and disconnect any time.
- **Interactive cards.** Sleep, workouts, training load and your plan render as cards in assistants that support MCP Apps.
- **19 tools**, from a daily brief to personal records and training load.
- **Plan changes with your OK.** An assistant can suggest changes to your training plan; nothing changes until you accept them in the app.

Tested by us in ChatGPT, Claude, Claude Code, Codex, Cursor, Grok, Perplexity and Gemini.

## Connect in two minutes

1. Install [P.R.O. on your iPhone](https://apps.apple.com/us/app/p-r-o/id6749865568), sign in and allow Apple Health.
2. Add the server to your assistant:

| Assistant | How to add it |
|---|---|
| ChatGPT | Install [P.R.O. from the ChatGPT plugin directory](https://chatgpt.com/plugins/plugin_asdk_app_6ad22f791530819196ed668dfdbf6909) · [guide](https://proapp.uk/apple-health-chatgpt) |
| Claude | Settings → Connectors → Add custom connector, URL `https://mcp.proapp.uk` · [guide](https://proapp.uk/apple-health-claude) |
| Claude Code | `claude mcp add --transport http pro https://mcp.proapp.uk` |
| Codex | `codex mcp add pro --url https://mcp.proapp.uk`, then `codex mcp login pro` · [guide](https://proapp.uk/apple-health-codex) |
| Cursor | Add `{ "mcpServers": { "pro": { "url": "https://mcp.proapp.uk" } } }` to `~/.cursor/mcp.json` · [guide](https://proapp.uk/apple-health-cursor) |
| Grok | grok.com → Connectors → add `https://mcp.proapp.uk` · [guide](https://proapp.uk/apple-health-grok) |
| Perplexity | Custom remote connector on perplexity.ai · [guide](https://proapp.uk/apple-health-perplexity) |
| Gemini, Manus, Cherry Studio and more | [All guides](https://proapp.uk/mcp-connect) |

3. When the assistant opens the sign-in page, open P.R.O. → Settings → MCP Connect → Get connection code and enter the code.

Outside the US? ChatGPT Health and Claude's Apple Health beta are US only; this connector is not. See [what works in your country](https://proapp.uk/apple-health-ai-outside-us).

## Things to ask

- "How did I sleep this week compared with last week?"
- "Am I recovered enough for intervals today?"
- "What are my fastest 5K and 10K this year?"
- "Summarize my training load for the last month."
- "Show my last run with pace and heart rate."

## Tools

19 tools in version 1.1.0. Machine-readable list: [proapp.uk/mcp/tools.json](https://proapp.uk/mcp/tools.json) · [changelog](https://proapp.uk/changelog)

| Tool | What it does |
|---|---|
| `get_daily_brief` | One day at a glance, today by default: activity so far, last night’s sleep, readiness with short reasons, training load zone, the planned session, your streak and any metric outside your usual range. |
| `get_daily_metrics` | Steps, active energy, distance, exercise minutes, flights, water, resting and average heart rate, HRV, sleep hours and sleep score. A recent period or exact dates, up to 90 days per call, per day or grouped by week or month. |
| `get_baselines` | Your usual range, average, latest value, deviation and trend for resting heart rate, HRV, sleep, steps and active energy over 28, 60 or 90 days. |
| `get_week_summary` | The last seven days compared with the seven before: steps, energy, exercise, sleep, resting heart rate, HRV and workout totals. |
| `get_workouts` | Workout summaries for a period or sport: type, date, duration, distance, energy, heart rate, pace, cadence, power, source app. |
| `get_records` | Records from up to 10 years of workouts: longest sessions, fastest pace or speed over standard distances, best week and month, yearly totals. |
| `get_training_load` | Seven-day acute versus 28-day chronic load, their ratio and trends, plus your readiness status. |
| `get_streak` | Current and longest run of active days. |
| `get_training_plan` | The active plan, upcoming sessions and the plan’s change history. |
| `get_plan_proposal` | A plan proposal with its changes and status: pending, accepted, partial, declined, expired or superseded. |
| `get_profile` | Name, sex and age; height and weight from Apple Health or the profile. |
| `get_goals` | Goals set in the app with targets and progress. |
| `recall` | Notes you or the P.R.O. coach saved. |
| `get_data_status` | What P.R.O. has received from your iPhone: last upload times, covered dates, tracked fields and which data categories you share. |
| `fetch_health_data` | On request, for one day or one workout: full-day heart-rate series, sleep stages, workout splits and heart-rate zones, GPS route. Uploaded by the phone when asked and kept for 48 hours; heart rate and sleep of the last 30 days and the latest 20 workouts are then kept for 7 days while you use an assistant. |
| `show_widget` | Shows a P.R.O. card in assistants that support MCP Apps: today, steps, sleep, heart, stats, compare, workouts, workout, streak, goals, plan, load, proposal, daily brief or personal records. |
| `propose_plan_changes` | Sends a new plan or changes to your current one as a pending proposal. Nothing changes until you accept it in P.R.O. |
| `remember_fact` | Saves one durable note (an injury, equipment, a decision). Works only if writing is enabled in the app. |
| `request_sync` | Asks the P.R.O. app on your iPhone to upload new Apple Health data. Returns the request status, not health data. |

## Hosted vs export-based Apple Health MCP servers

| | P.R.O. | Export-based servers |
|---|---|---|
| Setup | Add a URL, sign in with a code | Export Apple Health, run a server on a computer |
| Computer needed | No | Yes |
| Data freshness | Synced from your iPhone | As fresh as your last export |
| Works in phone assistant apps | Yes | Usually desktop only |
| Price | Free | Usually free and open source |

Prefer to keep everything on your own machine? An export-based open-source server is the better fit. Want it working everywhere with no upkeep? Use P.R.O.

## Your data

You pick the Apple Health categories the assistant can read, and you can disconnect at any time in P.R.O. under Settings → MCP Connect. P.R.O. does not sell your data, use it for advertising or train AI models on it. Details: [privacy policy](https://proapp.uk/privacy).

P.R.O. provides fitness and wellness information, not medical advice.

## Details

- **Server:** `https://mcp.proapp.uk`
- **Transport:** Streamable HTTP
- **Auth:** OAuth 2.1 with dynamic client registration and PKCE
- **Price:** free
- **Docs:** [Apple Health MCP guide](https://proapp.uk/apple-health-mcp) · [Connect guides](https://proapp.uk/mcp-connect) · [Privacy](https://proapp.uk/privacy) · [Terms](https://proapp.uk/terms)
- **Contact:** p.r.o.devel001@gmail.com

This repository holds the public [MCP Registry](https://registry.modelcontextprotocol.io) metadata for P.R.O. (`server.json`). The server itself is hosted.
