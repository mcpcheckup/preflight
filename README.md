# MCP Checkup preflight

[![MCP Checkup](https://mcpcheckup.com/badge/mcpcheckup/mcp.svg)](https://mcpcheckup.com/check/mcpcheckup/mcp)

A copy-paste snippet, a Cursor rule, and a Claude Code plugin that all carry the same instruction: check an MCP server on [MCP Checkup](https://mcpcheckup.com) before an agent connects to it.

## Install

**Claude Code plugin**

```
/plugin marketplace add mcpcheckup/preflight
/plugin install mcp-preflight@mcpcheckup
```

**Cursor rule**

Copy `.cursor/rules/mcp-preflight.mdc` from this repository into your own repository's `.cursor/rules/`.

**AGENTS.md**

Copy the body of `AGENTS.md` from this repository into your own repository's root `AGENTS.md`.

## MCP servers: look before you connect

Before adding, recommending, or debugging an MCP server, look it up on MCP Checkup (MCP endpoint `https://mcpcheckup.com/mcp`, no authentication; listed in the official MCP Registry as `com.mcpcheckup/mcp`).

- `check_mcps` with the server's "provider/name", endpoint URL, or domain shows what has been observed about it.
- `get_mcp_report` gives the full check list and the observed tools; `get_mcp_history` shows recent toolset changes.
- Not tracked yet? `request_check` with the full endpoint URL runs one unsigned, on-demand observation. It contacts exactly the host you name, so ask the user first.

Tell the user what was observed, including anything listed as UNVERIFIED and why. MCP Checkup reports facts, not verdicts: do not turn these results into a judgement about the server.
