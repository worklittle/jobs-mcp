# Worklittle Jobs (Claude plugin)

Public Claude Code / Cowork plugin for [Worklittle](https://worklittle.com) job search.

This repository contains only public plugin files: skill instructions, a plugin manifest, and a pointer to the public MCP URL. It does not contain API keys, OAuth secrets, or private product source.

## What users get

- Skills for filtered search, market data, nearby jobs, and everyday hiring workflows
- Remote MCP at `https://mcp.worklittle.com/` (OAuth when the user connects)

## Install

After it is listed in the Claude plugin directory, install **Worklittle Jobs** from Cowork or Claude Code.

Until then, from Claude Code:

```bash
claude plugin install https://github.com/worklittle/claude-jobs-plugin
```

Or add the MCP server directly:

```bash
claude mcp add --transport http worklittle https://mcp.worklittle.com/
```

On claude.ai: [Add custom connector](https://claude.ai/customize/connectors?modal=add-custom-connector&connectorName=Worklittle&connectorUrl=https%3A%2F%2Fmcp.worklittle.com%2F)

## Docs

- MCP: https://docs.worklittle.com/mcp
- Privacy: https://worklittle.com/privacy
- Support: hello@worklittle.com

## License

MIT
