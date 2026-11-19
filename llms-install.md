# Installing the Agent Loadout MCP server

Agent Loadout is a hosted, remote MCP server. There is nothing to clone, build or run locally.

1. Add this server to the MCP settings:

```json
{
  "mcpServers": {
    "loadout": {
      "url": "https://mcp.agentloadout.com/mcp",
      "type": "streamableHttp"
    }
  }
}
```

2. On first use the server answers 401 with an OAuth challenge. Let the client open the browser so the user signs in with their Loadout account (they can create one there; new accounts start with 100 free credits).

3. If the client cannot complete OAuth, ask the user for a Loadout API key (created in their Loadout account) and add it as a header:

```json
"headers": { "Authorization": "Bearer <LOADOUT_API_KEY>" }
```

4. Check the connection by calling the `account_status` tool. It returns the user's plan and credit balance.
