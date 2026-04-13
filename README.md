# MCP Verdict Demo

This repo demonstrates the [MCP Verdict Check](https://github.com/Thezenmonster/mcp-verdict-action) GitHub Action.

On every push and PR, the action scans MCP dependencies in `package.json` and returns trust verdicts (allow/warn/block) from the [AgentScore](https://agentscores.xyz) API.

## How it works

1. The workflow in `.github/workflows/mcp-check.yml` runs on push
2. The action reads `package.json` and finds MCP-related dependencies
3. For each dependency, it calls the AgentScore verdict API
4. If any package returns `block`, the check fails

## This repo's dependencies

| Package | Purpose |
|---------|---------|
| `@modelcontextprotocol/server-github` | Official GitHub MCP server |
| `exa-mcp-server` | Web search MCP server |
| `mcp-trust-guard` | Security middleware |

## Try it yourself

Add to any repo's workflow:

```yaml
- uses: Thezenmonster/mcp-verdict-action@v1
  with:
    fail-on: "block"
```

No API key needed. Free.

## Links

- [MCP Verdict Action](https://github.com/Thezenmonster/mcp-verdict-action)
- [AgentScore](https://agentscores.xyz)
- [API Docs](https://agentscores.xyz/docs)
# Capability governance test - 2026-04-13T09:53:36Z
