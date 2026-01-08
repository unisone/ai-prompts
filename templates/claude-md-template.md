# CLAUDE.md Project Template

## Description

A template for creating effective CLAUDE.md files that give AI coding agents the context they need. Based on patterns from Claude Code and production codebases.

## When to Use

- Starting any new project
- Adding AI coding assistant to existing project
- When Claude Code / Cursor / other agents struggle with your codebase

## Template

```markdown
# CLAUDE.md - [Project Name]

## Overview
[One paragraph describing what this project does and its primary purpose]

## Tech Stack
- **Language**: [TypeScript/Python/Go/etc]
- **Framework**: [React/Next.js/FastAPI/etc]
- **Database**: [PostgreSQL/MongoDB/etc]
- **Key Libraries**: [List 3-5 important ones]

## Project Structure
[Folder structure tree, focus on the important parts]
```
src/
├── components/    # React components
├── lib/           # Shared utilities
├── api/           # API routes
└── types/         # TypeScript types
```

## Key Commands
```bash
npm install        # Install deps
npm run dev        # Start dev server
npm run test       # Run tests
npm run typecheck  # Type checking
npm run lint       # Linting
```

## Conventions

### Code Style
- [List specific conventions: naming, file structure, etc]
- [Example: "Use kebab-case for file names"]
- [Example: "Prefer named exports over default exports"]

### Patterns
- [Describe patterns used in codebase]
- [Example: "Repository pattern for data access"]
- [Example: "Use React Query for server state"]

### What NOT to Do
- [Anti-patterns to avoid]
- [Example: "Don't use `any` type - use `unknown` or proper types"]
- [Example: "Don't commit directly to main"]

## Architecture Decisions

### [Decision 1: e.g., "State Management"]
We use [X] because [reason]. See [link to docs if any].

### [Decision 2: e.g., "Authentication"]
[Explain the approach and why]

## Common Tasks

### Adding a New Feature
1. Create types in `src/types/`
2. Add API route in `src/api/`
3. Create component in `src/components/`
4. Add tests

### Debugging
- Check logs at [location]
- Common issues: [list frequent problems and solutions]

## External Resources
- [Design docs, Figma, API specs]
- [Related repos]
```

## Why It Works

AI coding agents perform dramatically better when they understand:
1. **Structure**: Where to find and put things
2. **Conventions**: How to match existing code style
3. **Commands**: How to validate their work
4. **Context**: Why decisions were made

## Real Example

From a production Next.js app:

```markdown
# CLAUDE.md - Acme Dashboard

## Overview
Internal dashboard for Acme Corp. Shows sales metrics, manages users, handles billing.

## Tech Stack
- Next.js 14 (App Router)
- TypeScript 5
- Tailwind CSS + shadcn/ui
- Prisma + PostgreSQL
- Clerk for auth

## Conventions
- Use `@/` path alias for imports
- Components go in `src/components/[feature]/`
- Server actions in `src/actions/`
- All DB calls through Prisma, never raw SQL

## Commands
```bash
pnpm dev          # Dev server on :3000
pnpm db:push      # Push schema changes
pnpm db:studio    # Open Prisma Studio
```

## Important
- NEVER expose API keys in client components
- Always use server actions for mutations
- Run `pnpm typecheck` before committing
```

## Notes

- Keep it under 500 lines - agents have limited context
- Update it when conventions change
- Link to detailed docs rather than inlining everything
