# Installing the Drint MCP server

Drint is a hosted MCP server. There is nothing to clone, build or install, and no API key.

1. Add this entry to the MCP settings file (for Cline: `cline_mcp_settings.json`):

```json
{
  "mcpServers": {
    "drint": {
      "type": "streamableHttp",
      "url": "https://drint.io/mcp"
    }
  }
}
```

2. Check it works with a tool that needs no account: call `search_mockups` with `{"query": "kraft paper bag"}`. It returns a list of mockups.

3. Tools that use the person's Drint account (`get_dieline`, `make_dieline`, `list_my_projects`, `open_my_project`, `review_inbox`, `send_to_3d_studio`, `my_drint`) answer HTTP 401 with `WWW-Authenticate`. The client then opens the Drint sign-in page in the browser (OAuth 2.1, Dynamic Client Registration, PKCE). The person signs in there; never ask them for a password or token.

Docs: https://drint.io/help/mcp
