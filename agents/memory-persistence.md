# Memory & Context Persistence

> Techniques for maintaining context across sessions and managing long-running AI relationships.

## When to Use

- Working with AI on ongoing projects
- When you're tired of re-explaining context
- Building AI workflows that remember preferences
- Creating consistent AI personas/assistants

## Why It Works

AI doesn't remember between sessions by default. Every conversation starts fresh. By explicitly managing memory and context, you create continuity that makes AI dramatically more useful for real work.

## The Prompt

### Session Start - Context Loading

```
Before we begin, here's the context from our previous work:

**Project**: [Project name and description]
**Current Status**: [Where we left off]
**Key Decisions Made**: 
- [Decision 1]
- [Decision 2]
**Open Questions**:
- [Question 1]
**My Preferences**:
- [Preference 1 - e.g., "I prefer TypeScript over JavaScript"]
- [Preference 2 - e.g., "Keep responses concise"]

With this context, let's continue. [YOUR REQUEST]
```

### Session End - Memory Capture

```
Before we end, create a session summary I can use next time:

**What We Accomplished**:
- [List key completions]

**Decisions Made**:
- [List any decisions with reasoning]

**Current Status**:
- [Where things stand now]

**Next Steps**:
- [What should happen next]

**Open Questions**:
- [Unresolved items]

Format this so I can paste it at the start of our next conversation.
```

### Ongoing Context File Pattern

```
I maintain a context file for this project. Here it is:

---
PROJECT CONTEXT (Last updated: [DATE])

## Overview
[What this project is]

## Key Facts
- [Fact 1]
- [Fact 2]

## Decisions Log
- [Date]: [Decision] - Reasoning: [Why]

## My Preferences
- [Preference 1]
- [Preference 2]

## Current Focus
[What we're working on now]

## Don't Forget
- [Important reminder 1]
- [Important reminder 2]
---

Please reference this context throughout our conversation. If we make any decisions or learn anything important, remind me to update this file.
```

## Example

### For a Coding Project

```
PROJECT CONTEXT: MyApp Backend Refactor

## Overview
Refactoring a Node.js Express app to use TypeScript and clean architecture.

## Key Decisions
- 2026-01-15: Using Zod for validation (not Joi) - better TS integration
- 2026-01-20: Repository pattern for data access
- 2026-01-25: Keeping Express (not migrating to Fastify) - team familiarity

## Tech Stack
- Node.js 22, TypeScript 5.4, Express 5
- PostgreSQL, Drizzle ORM
- Jest for testing

## My Preferences
- Prefer explicit over clever
- Always add JSDoc comments
- Test files next to source files

## Current Status
- Auth module: DONE
- User module: IN PROGRESS (crud done, need validation)
- Posts module: NOT STARTED

## Next Up
Add input validation to user endpoints using Zod

---

Continue with the user module validation work.
```

### For Writing Projects

```
WRITING PROJECT CONTEXT: Blog Series on AI Tools

## Overview
8-part series on AI tools for productivity

## Voice/Style
- Conversational but authoritative
- Use "you" not "one"
- Short paragraphs (3-4 sentences max)
- Always include practical examples

## Published
1. "AI for Email" - Published 1/10
2. "AI for Writing" - Published 1/17

## In Progress
3. "AI for Coding" - Draft 60% done

## Research Collected
- Cursor vs Copilot stats (saved in research-coding.md)
- User quotes from Reddit threads

## Avoid
- Don't mention ChatGPT too much (overexposed)
- Don't use "game-changer" or "revolutionary"

---

Let's continue the AI for Coding draft. We left off at the section about debugging.
```

## Advanced Patterns

### The Living Document Pattern

```
We maintain a shared document. At any point, I may ask you to:

- "Update the context with [new information]"
- "What does our context say about [topic]?"
- "Remove [outdated information] from context"

Always reference this context when answering questions about the project.

Current context:
[PASTE CONTEXT]
```

### The Preference Learning Pattern

```
As we work together, learn my preferences:

When I correct you or express a preference, remember it. For example:
- If I say "make it shorter," note that I prefer concise responses
- If I choose option A over B, note my decision criteria

At the end of our session, summarize any preferences you learned so I can add them to my context file.
```

### The Project State Machine

```
This project has defined states:

STATES:
1. RESEARCH - Gathering information
2. PLANNING - Creating approach
3. IMPLEMENTATION - Building
4. REVIEW - Checking work
5. DONE - Complete

CURRENT STATE: [STATE]

When transitioning states, confirm with me first. When answering, consider what state we're in (e.g., don't jump to implementation during research).
```

## Pro Tips

1. **Keep context files in your repo** — Version control your AI context
2. **Update after each session** — Stale context is worse than no context
3. **Be specific about preferences** — "I prefer X" > "I like clean code"
4. **Include anti-preferences** — What you DON'T want is equally important
5. **Timestamp decisions** — Helps you remember why you decided things

## Context File Template

```markdown
# [PROJECT NAME] - AI Context

Last Updated: YYYY-MM-DD

## Quick Summary
[One paragraph about the project]

## Tech Stack / Tools
- [Tool 1]
- [Tool 2]

## Key Decisions
| Date | Decision | Reasoning |
|------|----------|-----------|
| | | |

## My Preferences  
- [ ] Preference 1
- [ ] Preference 2

## Current Status
[What's done, what's in progress]

## Next Session
[What to work on next]

## Notes
[Anything else important]
```

## Effectiveness

| Use Case | Impact |
|----------|--------|
| Ongoing projects | ⭐⭐⭐⭐⭐ |
| Consistent personas | ⭐⭐⭐⭐⭐ |
| Team AI workflows | ⭐⭐⭐⭐ |
| One-off tasks | ⭐⭐ |

---

*Essential pattern for treating AI as a long-term collaborator rather than a one-shot tool*
