# Explain Codebase

## Description

Understand an unfamiliar codebase quickly. Maps architecture, identifies patterns, and explains how components connect.

## Prompt

```
Help me understand this codebase.

## Context

{{context}}

## Files/Code

{{code}}

---

## Analysis Framework

### 1. High-Level Overview

**What does this code do?**
(One paragraph summary)

**Architecture Pattern:**
(MVC, Clean Architecture, Feature-based, etc.)

**Key Technologies:**
- Framework:
- Database:
- External Services:

### 2. Entry Points

Where does execution start?
- Main entry file:
- Request handling:
- Event triggers:

### 3. Data Flow

How does data move through the system?

```
[User Action] 
    → [Entry Point] 
    → [Business Logic] 
    → [Data Layer] 
    → [Response]
```

### 4. Key Abstractions

| Abstraction | Purpose | Example |
|-------------|---------|--------|
| | | |

### 5. Dependencies

**Internal Dependencies:**
- What depends on what?
- Which modules are core vs peripheral?

**External Dependencies:**
- Third-party libraries and their purpose
- External services/APIs

### 6. Patterns Used

| Pattern | Where | Why |
|---------|-------|-----|
| | | |

### 7. Potential Gotchas

- Non-obvious behaviors
- Implicit conventions
- Technical debt to be aware of

### 8. Where to Make Changes

If I wanted to:
- Add a new feature: Start in...
- Fix a bug in X: Look at...
- Change data model: Modify...

### 9. Questions I Still Have

- [List any unclear areas]
```

## Variables

- `{{context}}`: What you know about the codebase (project name, purpose, tech stack)
- `{{code}}`: Key files to analyze (entry points, main modules, or specific files you're confused about)

## Example Usage

```
Help me understand this codebase.

## Context

This is a Next.js e-commerce app. I need to add a new payment provider but I don't understand how the current payment flow works.

## Files/Code

[Paste: checkout page, payment service, API routes]
```

## For Large Codebases

Start with:
1. `package.json` or equivalent (dependencies)
2. Main entry point
3. Folder structure overview
4. One complete feature flow (e.g., user registration)

Then dive deeper into specific areas.

## Notes

- Ask follow-up questions about unclear areas
- Request specific files as needed
- Understanding > speed - take time to map dependencies
- Look for README, docs, or comments first
