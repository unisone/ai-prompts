# Technical Documentation

## Description

Write clear technical documentation including READMEs, API docs, architecture docs, and runbooks. Produces documentation that developers actually read.

## Prompt

```
Write technical documentation for:

## Subject

{{subject}}

## Documentation Type

{{doc_type}}

## Audience

{{audience}}

---

## Documentation Guidelines

### Structure

1. **Start with the "What" and "Why"**
   - What is this?
   - Why does it exist?
   - What problem does it solve?

2. **Quick Start (30 seconds to value)**
   - Minimal steps to get something working
   - Copy-paste ready commands
   - Expected output so reader knows it worked

3. **Core Concepts**
   - Key terms and definitions
   - Mental model for how it works
   - Architecture diagram if helpful

4. **Common Use Cases**
   - Real examples with code
   - Cover 80% of what users will do

5. **Reference**
   - Complete API/configuration options
   - Organized for scanning, not reading

6. **Troubleshooting**
   - Common errors and fixes
   - FAQ

### Writing Style

- Use active voice ("Run the command" not "The command should be run")
- One idea per sentence
- Short paragraphs (3-4 lines max)
- Code examples > lengthy explanations
- Use second person ("you") for instructions

### Formatting

- Use headers for scanability
- Code blocks with language hints for syntax highlighting
- Tables for comparing options
- Callouts for warnings/tips
- Links to related docs

### What to Avoid

- Jargon without explanation
- Assumptions about prior knowledge
- "Simply" or "just" (if it were simple, they wouldn't need docs)
- Outdated information
- Walls of text
```

## Variables

- `{{subject}}`: What you're documenting (library, API, system, feature)
- `{{doc_type}}`: README, API Reference, Architecture Doc, Runbook, Tutorial
- `{{audience}}`: Who will read this (new developers, API consumers, ops team)

## Doc Type Templates

### README Template
```markdown
# Project Name

One-line description of what this does.

## Quick Start

[3-5 steps to get running]

## Installation

## Usage

## Configuration

## Contributing

## License
```

### API Endpoint Template
```markdown
## Endpoint Name

`POST /api/v1/resource`

Description of what this endpoint does.

### Request

### Response

### Errors

### Example
```

### Runbook Template
```markdown
# [Incident Type] Runbook

## Symptoms

## Impact

## Quick Mitigation

## Investigation Steps

## Resolution

## Prevention
```

## Notes

- Write for scanning first, reading second
- Update docs when code changes (or they become lies)
- Test your own instructions on a fresh environment
- Good docs reduce support burden
