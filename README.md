# Drint MCP server

Packaging design in your AI chat: 3D box and bag mockups, and print-ready FEFCO / ECMA dielines at any size.

[Drint](https://drint.io) is a packaging and print design studio. This is its hosted MCP server. Nothing to install: add the URL to your MCP client.

```text
https://drint.io/mcp
```

- Transport: Streamable HTTP
- Auth: OAuth 2.1, only when a tool needs your account (Dynamic Client Registration and Client ID Metadata Documents, PKCE S256)
- Official MCP Registry: `io.drint/drint`
- Docs: https://drint.io/help/mcp

This repository holds documentation only. The server is run by Drint.

## Add it

**Claude** (claude.ai, desktop): Customize → Connectors → Add custom connector → `https://drint.io/mcp`

**ChatGPT**: Settings → Apps & Connectors → Advanced settings → turn on Developer mode → Create → `https://drint.io/mcp`, OAuth

**Claude Code**

```bash
claude mcp add --transport http drint https://drint.io/mcp
```

**Cursor** (`~/.cursor/mcp.json`)

```json
{
  "mcpServers": {
    "drint": { "url": "https://drint.io/mcp" }
  }
}
```

**VS Code / GitHub Copilot** (`.vscode/mcp.json`), or search "drint" in the MCP server gallery

```json
{
  "servers": {
    "drint": { "type": "http", "url": "https://drint.io/mcp" }
  }
}
```

**Perplexity, Grok, Le Chat, Meta Muse**: add a custom remote connector with the same URL and choose OAuth.

## Tools

| Tool | Account | What it does |
|---|---|---|
| `search_mockups` | no | Search about a thousand ready 3D packaging and print mockups |
| `open_mockup` | no | Show one in an interactive 3D viewer (MCP Apps): rotate, recolour, resize |
| `list_dielines` | no | 67 Drint structures and about 180 FEFCO / ECMA codes, with default sizes |
| `get_dieline` | yes | Print-ready PDF / AI or SVG dieline at an exact size, cut and crease as spot colours |
| `make_dieline` | yes (Pro) | DXF and CF2 for cutting tables and die-makers |
| `list_my_projects` | yes | Your Drint projects with thumbnails |
| `open_my_project` | yes | One of your projects in 3D with your artwork on it |
| `review_inbox` | yes | Work waiting for you in your Drint review inbox |
| `send_to_3d_studio` | yes | A link that stages a project in Drint 3D Studio |
| `my_drint` | yes | Your plan and the downloads left this month |

Tools that need an account answer HTTP 401 with `WWW-Authenticate`, so your AI opens the Drint sign-in page. Your AI never sees your Drint password. Remove access any time in Drint → Account → Sign-in & security → Connected apps.

## Try

- "Find kraft paper bag mockups on Drint and show the first one in 3D."
- "Which FEFCO codes does Drint draw for shipping cartons?"
- "Give me a FEFCO 0201 dieline for 400 × 300 × 250 mm as a PDF."
- "Show my Drint projects and open the tea box in 3D."

## Plans

Mockups and dieline structures are free without an account. A free Drint account includes 3 PDF / SVG dielines a month; Drint Pro removes the limits and adds DXF / CF2. See https://drint.io.

## Support

support@drint.io · [Privacy](https://drint.io/privacy) · [Terms](https://drint.io/terms)
