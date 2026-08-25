# Worklittle Jobs

Swipe to apply for jobs using the Worklittle MCP app, and search over 4 million jobs with filters like visa status, distance, and salary, and connect your Worklittle account to save jobs you love.

Public MCP connector and plugin files for [Worklittle](https://worklittle.com). This repository contains skill instructions, a plugin manifest, and a pointer to the public MCP URL. It does not contain API keys, OAuth secrets, or private product source.

## What users get

- Remote MCP at `https://mcp.worklittle.com/`
- Search with visa, distance, salary, and other filters
- Connect a Worklittle account to save jobs

## Connect

Remote Streamable HTTP (any MCP client):

```
https://mcp.worklittle.com/
```

Add that URL in ChatGPT, VS Code, Cursor, Claude, Codex, or another app that supports remote MCP. Docs for each client: https://docs.worklittle.com/mcp

Claude Code (this is the Claude CLI, not the connector name):

```bash
claude mcp add --transport http worklittle https://mcp.worklittle.com/
```

Docs: https://docs.worklittle.com/mcp  
Privacy: https://worklittle.com/privacy  
Support: hello@worklittle.com


## Cursor plugin

This repo follows the [Cursor plugin template](https://github.com/cursor/plugin-template) as a **single plugin** at the repository root:

- `.cursor-plugin/plugin.json`
- `.cursor-plugin/marketplace.json` (one plugin, `source: "."`)
- `mcp.json` (remote MCP at `https://mcp.worklittle.com/`)
- `skills/` (YAML frontmatter on every `SKILL.md`)
- `rules/worklittle-jobs.mdc`
- `assets/logo.png`

Validate before marketplace review:

```bash
node scripts/validate-template.mjs
```

## Agent skills

Install the public job-search skills into Cursor, Codex, Claude Code, and other agents:

```bash
npx skills add worklittle/jobs-mcp
```

Browse them on [skills.sh](https://skills.sh). Docs also publish skills at `https://docs.worklittle.com`.

## License

MIT

## Directories

Listed in the [Claude Market MCP directory](https://www.claudemarket.ai/mcp).
