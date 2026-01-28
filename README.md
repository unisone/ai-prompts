<div align="center">

# AI Prompt Library

**Battle-tested prompts for Claude, GPT, and Gemini**

[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Prompts](https://img.shields.io/badge/Prompts-46-green.svg)](#quick-reference)
[![Claude 4.5](https://img.shields.io/badge/Claude_4.5-Optimized-blueviolet.svg)](#2026-updates)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

[Quick Start](#quick-start) | [Browse Prompts](#quick-reference) | [By Problem](#browse-by-problem) | [Contributing](#contributing)

</div>

---

## 🆕 2026 Updates

**Claude 4.5 changed everything.** The new model is more literal and precise — old prompts that relied on Claude "filling in the blanks" now underperform. We've added 5 new techniques optimized for 2026:

| Technique | What It Does |
|-----------|-------------|
| [XML Structured](./techniques/xml-structured.md) | Structure prompts with tags Claude natively understands |
| [Extended Thinking](./techniques/extended-thinking.md) | Force step-by-step reasoning for complex problems |
| [Self-Correcting](./techniques/self-correcting.md) | Built-in verification to catch hallucinations |
| [Anti-Botspeak](./techniques/anti-botspeak.md) | Avoid phrases that scream "AI wrote this" |
| [Permission to Fail](./techniques/permission-to-fail.md) | Get honest "I don't know" instead of confident lies |

---

## Table of Contents

- [Quick Start](#quick-start)
- [Quick Reference](#quick-reference)
- [Browse by Problem](#browse-by-problem)
- [Browse by Category](#browse-by-category)
  - [Coding](#coding)
  - [Techniques](#techniques)
  - [Writing](#writing)
  - [Analysis](#analysis)
  - [Agents](#agents) 🆕
  - [Sales](#sales) 🆕
  - [Marketing](#marketing) 🆕
  - [Images](#images) 🆕
- [Prompt Format](#prompt-format)
- [Pro Prompts](#pro-prompts-for-sponsors)
- [Contributing](#contributing)

---

## Quick Start

```bash
# Clone
git clone https://github.com/unisone/ai-prompts.git

# Or copy any prompt directly from GitHub
```

Each prompt includes: **Description** | **When to Use** | **The Prompt** | **Why It Works** | **Example**

---

## Quick Reference

All 29 prompts at a glance:

| Prompt | Problem Solved | File |
|--------|---------------|------|
| **Techniques** | | |
| [Self-Critique](#self-critique) | AI outputs have errors you catch too late | [techniques/self-critique.md](./techniques/self-critique.md) |
| [Decomposition](#decomposition) | Complex tasks produce incomplete solutions | [techniques/decomposition.md](./techniques/decomposition.md) |
| [Context-First](#context-first) | AI jumps to solutions without understanding | [techniques/context-first.md](./techniques/context-first.md) |
| [Concise Output](#concise-output) | Responses are too verbose | [techniques/concise-output.md](./techniques/concise-output.md) |
| [Literal Instructions](#literal-instructions) | Claude 4.x gives minimal responses | [techniques/literal-instructions.md](./techniques/literal-instructions.md) |
| [Interview First](#interview-first) | Vague requests produce wrong outputs | [techniques/interview-first.md](./techniques/interview-first.md) |
| [Deep Reasoning](#deep-reasoning) | Complex problems need thorough analysis | [techniques/deep-reasoning.md](./techniques/deep-reasoning.md) |
| [GPT to Claude](#gpt-to-claude) | GPT prompts underperform in Claude | [techniques/gpt-to-claude-converter.md](./techniques/gpt-to-claude-converter.md) |
| [XML Structured](#xml-structured) | Complex prompts get inconsistent results | [techniques/xml-structured.md](./techniques/xml-structured.md) |
| [Extended Thinking](#extended-thinking) | Need thorough analysis on complex problems | [techniques/extended-thinking.md](./techniques/extended-thinking.md) |
| [Self-Correcting](#self-correcting) | AI hallucinations cost you time | [techniques/self-correcting.md](./techniques/self-correcting.md) |
| [Anti-Botspeak](#anti-botspeak) | AI text sounds obviously AI-generated | [techniques/anti-botspeak.md](./techniques/anti-botspeak.md) |
| [Permission to Fail](#permission-to-fail) | Confident wrong answers | [techniques/permission-to-fail.md](./techniques/permission-to-fail.md) |
| **Coding** | | |
| [Code Review Checklist](#code-review-checklist) | Missing bugs in code review | [coding/code-review-checklist.md](./coding/code-review-checklist.md) |
| [Code Review Expert](#code-review-expert) | Nitpicky reviews miss real issues | [coding/code-review-expert.md](./coding/code-review-expert.md) |
| [Systematic Debugging](#systematic-debugging) | Chasing wrong causes when debugging | [coding/debug-systematic.md](./coding/debug-systematic.md) |
| [Safe Refactoring](#safe-refactoring) | Breaking things when refactoring | [coding/refactor-safely.md](./coding/refactor-safely.md) |
| [API Endpoint Design](#api-endpoint-design) | Inconsistent API design | [coding/api-endpoint-design.md](./coding/api-endpoint-design.md) |
| [Test Generator](#test-generator) | Missing test coverage | [coding/test-generator.md](./coding/test-generator.md) |
| [Explain Codebase](#explain-codebase) | Lost in unfamiliar code | [coding/explain-codebase.md](./coding/explain-codebase.md) |
| [Code Craftsman](#code-craftsman) | Generic AI-generated code | [coding/ultrathink-code-craftsman.md](./coding/ultrathink-code-craftsman.md) |
| [Structured Reasoning](#structured-reasoning) | Disorganized problem solving | [coding/structured-reasoning-planner.md](./coding/structured-reasoning-planner.md) |
| [Agentic Patterns](#agentic-patterns) | AI coding agents fail on complex tasks | [coding/agentic-coding-patterns.md](./coding/agentic-coding-patterns.md) |
| [Startup Velocity](#startup-velocity) | Need to ship fast without breaking | [coding/startup-velocity.md](./coding/startup-velocity.md) |
| **Writing** | | |
| [Technical Documentation](#technical-documentation) | Poor or missing docs | [writing/technical-documentation.md](./writing/technical-documentation.md) |
| [Resume Architect](#resume-architect) | Resume not getting interviews | [writing/ultrathink-resume-architect.md](./writing/ultrathink-resume-architect.md) |
| **Analysis & Research** | | |
| [Data Insights](#data-insights) | Data but no actionable insights | [analysis/data-insights.md](./analysis/data-insights.md) |
| [SQL Query Builder](#sql-query-builder) | Writing complex SQL queries | [analysis/sql-query-builder.md](./analysis/sql-query-builder.md) |
| [Market Research](#market-research) | Need comprehensive market analysis | [research/market-research.md](./research/market-research.md) |
| [Competitor Analysis](#competitor-analysis) | Understanding competitive landscape | [research/competitor-analysis.md](./research/competitor-analysis.md) |
| **Creative** | | |
| [Brainstorm Ideas](#brainstorm-ideas) | Stuck on first obvious solution | [creative/brainstorm-ideas.md](./creative/brainstorm-ideas.md) |
| [Naming Generator](#naming-generator) | Need memorable product/feature name | [creative/naming-generator.md](./creative/naming-generator.md) |
| **Templates** | | |
| [CLAUDE.md Template](#claude-md-template) | AI agents struggle with your codebase | [templates/claude-md-template.md](./templates/claude-md-template.md) |
| [Example Prompt](#example-prompt) | How to format new prompts | [templates/example-prompt.md](./templates/example-prompt.md) |
| **Agents** 🆕 | | |
| [Orchestration Patterns](#orchestration-patterns) | Complex tasks need multiple perspectives | [agents/orchestration-patterns.md](./agents/orchestration-patterns.md) |
| [Plan-Then-Execute](#plan-then-execute) | AI dives in without thinking | [agents/plan-then-execute.md](./agents/plan-then-execute.md) |
| [Memory Persistence](#memory-persistence) | Context lost between sessions | [agents/memory-persistence.md](./agents/memory-persistence.md) |
| **Sales** 🆕 | | |
| [Discovery Call Framework](#discovery-call) | Unstructured sales conversations | [sales/discovery-call.md](./sales/discovery-call.md) |
| [Objection Handling](#objection-handling) | Stuck when prospects push back | [sales/objection-handling.md](./sales/objection-handling.md) |
| [Cold Outreach](#cold-outreach) | Low response rates on outreach | [sales/cold-outreach.md](./sales/cold-outreach.md) |
| **Marketing** 🆕 | | |
| [Hook Generator](#hook-generator) | Content doesn't grab attention | [marketing/hook-generator.md](./marketing/hook-generator.md) |
| [Content Repurposing](#content-repurposing) | Creating content takes too long | [marketing/content-repurposing.md](./marketing/content-repurposing.md) |
| [Ad Copy Frameworks](#ad-copy-frameworks) | Ads don't convert | [marketing/ad-copy-frameworks.md](./marketing/ad-copy-frameworks.md) |
| **Images** 🆕 | | |
| [Photo-Realistic](#photo-realistic) | AI images look fake | [images/photo-realistic.md](./images/photo-realistic.md) |
| [Style Consistency](#style-consistency) | Each image looks different | [images/style-consistency.md](./images/style-consistency.md) |
| [Product Mockups](#product-mockups) | Need product photos fast | [images/product-mockups.md](./images/product-mockups.md) |

---

## Browse by Problem

### I need better AI output quality

| Problem | Solution | Link |
|---------|----------|------|
| AI makes errors I catch too late | Have it self-critique before finalizing | [Self-Critique](./techniques/self-critique.md) |
| Complex tasks come back incomplete | Break into sub-problems first | [Decomposition](./techniques/decomposition.md) |
| AI jumps to wrong solutions | Force context gathering before solving | [Context-First](./techniques/context-first.md) |
| Responses are too long/verbose | Explicit output constraints | [Concise Output](./techniques/concise-output.md) |
| Claude 4.x gives minimal answers | Request explicit scope expansion | [Literal Instructions](./techniques/literal-instructions.md) |

### I need help with code

| Problem | Solution | Link |
|---------|----------|------|
| Missing bugs in review | Systematic 10-point checklist | [Code Review](./coding/code-review-checklist.md) |
| Debugging takes forever | 8-step root cause methodology | [Debugging](./coding/debug-systematic.md) |
| Afraid to refactor | 5-phase safe refactoring | [Refactoring](./coding/refactor-safely.md) |
| Inconsistent API design | REST/GraphQL design template | [API Design](./coding/api-endpoint-design.md) |
| Low test coverage | Generate happy path + edge cases | [Test Generator](./coding/test-generator.md) |
| Lost in new codebase | 9-part codebase analysis | [Explain Codebase](./coding/explain-codebase.md) |

### I need help with writing

| Problem | Solution | Link |
|---------|----------|------|
| Documentation is lacking | README, API docs, runbook templates | [Technical Docs](./writing/technical-documentation.md) |
| Resume not converting | ATS-optimized resume builder | [Resume Architect](./writing/ultrathink-resume-architect.md) |

### I need help with analysis

| Problem | Solution | Link |
|---------|----------|------|
| Data but no insights | Patterns, anomalies, actions framework | [Data Insights](./analysis/data-insights.md) |

---

## Browse by Category

### Coding

8 prompts for development workflows.

| Prompt | Description |
|--------|-------------|
| [code-review-checklist.md](./coding/code-review-checklist.md) | 10-point review covering logic, security, performance |
| [debug-systematic.md](./coding/debug-systematic.md) | 8-step methodology to find root cause |
| [refactor-safely.md](./coding/refactor-safely.md) | 5-phase approach: assess, safety net, change, verify, cleanup |
| [api-endpoint-design.md](./coding/api-endpoint-design.md) | REST/GraphQL endpoint design template |
| [test-generator.md](./coding/test-generator.md) | Generate happy path, boundary, error tests |
| [explain-codebase.md](./coding/explain-codebase.md) | Understand unfamiliar codebases systematically |
| [ultrathink-code-craftsman.md](./coding/ultrathink-code-craftsman.md) | Philosophy-driven system prompt |
| [structured-reasoning-planner.md](./coding/structured-reasoning-planner.md) | 9-step structured reasoning framework |

### Techniques

5 meta-prompting methods backed by research.

| Prompt | Research Basis |
|--------|----------------|
| [self-critique.md](./techniques/self-critique.md) | Self-criticism improves accuracy (Schulhoff, Learn Prompting) |
| [decomposition.md](./techniques/decomposition.md) | Breaking problems into parts improves complex task completion |
| [context-first.md](./techniques/context-first.md) | Context is underrated and massively impactful (OpenAI) |
| [concise-output.md](./techniques/concise-output.md) | Models overcompensate when instructions are vague |
| [literal-instructions.md](./techniques/literal-instructions.md) | Claude 4.x takes instructions literally (Anthropic) |

### Writing

2 prompts for documentation and professional writing.

| Prompt | Description |
|--------|-------------|
| [technical-documentation.md](./writing/technical-documentation.md) | README, API docs, runbook templates |
| [ultrathink-resume-architect.md](./writing/ultrathink-resume-architect.md) | ATS-optimized resume optimization |

### Analysis

1 prompt for data analysis.

| Prompt | Description |
|--------|-------------|
| [data-insights.md](./analysis/data-insights.md) | Extract patterns, anomalies, and actionable recommendations |

---

## Prompt Format

Every prompt follows this structure:

```markdown
# Prompt Name

## Description
What this prompt does.

## When to Use
Specific scenarios where this prompt helps.

## Prompt
The actual prompt text to copy/paste.

## Why It Works
Research or reasoning behind the technique.

## Example
Real usage showing input and output.

## Notes
Tips and limitations.
```

---

## Pro Prompts for Sponsors

These prompts built a 577-file production app with 0 critical bugs.

[![Sponsor](https://img.shields.io/badge/Unlock_Pro_Prompts-$5/month-EA4AAA?style=for-the-badge&logo=githubsponsors)](https://github.com/sponsors/unisone)

| Free (This Repo) | Pro (Sponsors Only) |
|------------------|---------------------|
| 17 production prompts | System prompts I use daily |
| Research-backed techniques | Multi-file refactoring patterns |
| | Ship Feature in 2 Hours workflow |
| | Senior code review (catches security issues) |
| | New prompts added monthly |

---

## Contributing

1. Fork the repository
2. Create a prompt using the [template](./templates/example-prompt.md)
3. Submit a PR

See [CONTRIBUTING.md](CONTRIBUTING.md) for details.

---

<div align="center">

**Built by [Alex Zaytsev](https://github.com/unisone)**

Star this repo if you find it useful

</div>

---

## 🔐 Want More?

**[AI Prompts Pro](https://github.com/sponsors/unisone)** — Premium prompts for sponsors:

| What You Get | Free | Pro |
|--------------|------|-----|
| Basic prompts | ✅ | ✅ |
| System prompts (Claude Code, Cursor) | ❌ | ✅ |
| Enterprise patterns | ❌ | ✅ |
| Production templates (SaaS, CLI) | ❌ | ✅ |
| Parallel agent orchestration | ❌ | ✅ |
| Monthly updates | ❌ | ✅ |

**[Become a Sponsor →](https://github.com/sponsors/unisone)**

