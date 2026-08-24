---
name: setup
description: >-
  Connect Worklittle MCP (OAuth) so job search tools work. Use when the user just
  installed this plugin, MCP is disconnected, or they need to sign in to Worklittle.
---

# Set up Worklittle Jobs

## What this plugin uses

Remote MCP at `https://mcp.worklittle.com/` (OAuth). No API key is stored in this plugin.

Public docs: https://docs.worklittle.com/mcp
Privacy: https://worklittle.com/privacy
Product: https://worklittle.com

## Connect

Use the same URL in any MCP client (ChatGPT, VS Code, Cursor, Claude, Codex, and others):

```
https://mcp.worklittle.com/
```

1. Add a remote / HTTP MCP server named Worklittle with that URL.
2. Complete OAuth in the browser (same Worklittle account as worklittle.com).
3. Confirm tools such as `search_jobs` are available, then run a small search.

Claude Code only (the `claude` CLI):

```bash
claude mcp add --transport http worklittle https://mcp.worklittle.com/
```

If OAuth fails in Claude.ai, add a custom connector: Customize → Connectors → `https://mcp.worklittle.com/`
