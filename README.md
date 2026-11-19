<p align="center"><img src="logo.png" width="96" alt="Agent Loadout"></p>

# Agent Loadout MCP server

Agent Loadout is a hosted MCP server for agencies, freelancers and consultants. Connect it to ChatGPT, Claude, Claude Code, Codex or any client that speaks remote MCP, and your AI gets:

- **800+ tools of live business data**: Google and Maps rankings, keyword volumes, backlinks, competitor ad libraries, reviews, verified contacts and what AI assistants answer about a business.
- **62 step by step methods** that turn the data into client work: finding businesses with a visible gap, SEO and local visibility audits, Google Maps grids, competitor ad research, website teardowns, proposals and monthly client reports.

Every job shows its cost before it runs, and nothing is sent or posted without your yes. You start free with 100 credits; Pro is $29 a month with 2,900 credits. More at [agentloadout.com/mcp](https://agentloadout.com/mcp).

## Server

```
https://mcp.agentloadout.com/mcp
```

Streamable HTTP. Sign in with your Loadout account (OAuth) when your client asks; you can create the account during sign-in. Clients that cannot do OAuth can send an API key instead (`Authorization: Bearer <key>`); you create the key in your Loadout account.

Listed in the official MCP Registry as `com.agentloadout/agent-loadout`.

## Connect

**ChatGPT**: open Plugins, click the plus button, choose "Add custom MCP server", name it Loadout and paste the server address. Sign in when asked.

**Claude**: Customize, then Connectors, "+ Add", "Add custom connector". Name it Loadout, paste the server address, then Connect and sign in.

**Claude Code**: the [Loadout plugin](https://github.com/agentloadout/loadout) adds the server and Loadout's methods:

```
/plugin marketplace add agentloadout/loadout
/plugin install loadout@loadout
```

Or the server alone: `claude mcp add --transport http loadout https://mcp.agentloadout.com/mcp`

**Codex**: add to `~/.codex/config.toml`, and set `LOADOUT_API_KEY` in your shell profile:

```toml
[mcp_servers.loadout]
url = "https://mcp.agentloadout.com/mcp"
bearer_token_env_var = "LOADOUT_API_KEY"
```

**Cursor, VS Code, Cline, Windsurf and other clients** (see [`.mcp.json`](.mcp.json)):

```json
{
  "mcpServers": {
    "loadout": {
      "url": "https://mcp.agentloadout.com/mcp"
    }
  }
}
```

If your client does not open a sign-in window, add `"headers": { "Authorization": "Bearer YOUR_LOADOUT_API_KEY" }`.

## What to ask

- "Find dentists in Austin who are losing on Google Maps, with the owner's email."
- "Run an SEO audit of acme.com against its three closest competitors."
- "Which ads have my client's competitors kept running the longest, and why do they work?"
- "Does ChatGPT recommend my client's business, and which pages does it quote instead?"

## Links

- Website: https://agentloadout.com
- Setup guide: https://agentloadout.com/setup
- Terms: https://app.agentloadout.com/terms
- Privacy: https://app.agentloadout.com/privacy
- Support and security: info@agentloadout.com

This repository holds the connection details only. The server is hosted by Loadout (Envision Digital s. r. o.).
