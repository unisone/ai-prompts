# MCP Server Planner

> Design a Model Context Protocol server the right way: tools first, protocol second.

## When to Use

- Exposing an API, database, or service to Claude Code / Claude Desktop
- Deciding what should be a tool vs. a resource vs. a prompt
- Scoping an MCP server before writing code
- Reviewing an existing MCP server that's grown messy

## Why It Works

Most bad MCP servers fail at design, not implementation: tools with vague descriptions the model never calls, overlapping tools that confuse routing, or read/write operations with no safety boundaries. Forcing tool-first design — names, descriptions, schemas, and trigger conditions up front — catches these problems when they're still cheap to fix.

## The Prompt

```
Help me design an MCP server before I write any code.

**What I'm exposing:** [API / database / service — describe it in 2-3 sentences]
**Who uses it:** [me in Claude Code / a team / published for others]
**Transports:** [stdio for local use, HTTP for remote, or both]

**Step 1 — Tool inventory.**
Propose the tool list. For each tool:
- name: snake_case verb-first name (e.g. search_issues, not issues)
- description: one line the MODEL will read — include WHEN to call it and when NOT to
- input schema: parameters with types, required vs optional
- read-only or mutating (mark mutating tools clearly)

Rules: one tool = one job. If two tools overlap, merge or differentiate them
explicitly. Aim for 5-12 tools; more than that usually means the domain needs
splitting into two servers.

**Step 2 — Resources vs tools.**
Tell me what should be an MCP Resource (relatively static, referenceable
content like schemas or docs) instead of a tool, and why.

**Step 3 — Safety boundaries.**
For every mutating tool: what confirmation or guardrail should exist?
(confirm-before-write, dry-run mode, scoped credentials, audit logging)

**Step 4 — Description review.**
Rewrite any tool description that a model could misroute. A good description
names the trigger situation AND the exclusion ("Use when X. Don't use for Y —
that's what <other-tool> is for.").

Output: a server spec in markdown with the tool table, schemas as JSON Schema
fragments, and a build checklist I can hand to a coding agent.
```
