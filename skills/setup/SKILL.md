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

1. Enable the Worklittle Jobs plugin if it installed disabled.
2. Approve the Worklittle MCP server when Claude asks.
3. Complete OAuth in the browser (same Worklittle account as worklittle.com).
4. Confirm tools such as `search_jobs` are available, then run a small search.

If OAuth fails, add a custom connector in Claude: Customize → Connectors → `https://mcp.worklittle.com/`

Claude Code:

```bash
claude mcp add --transport http worklittle https://mcp.worklittle.com/
```
