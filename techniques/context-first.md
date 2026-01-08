# Context-First Investigation

## Description

Research shows that providing more relevant context "can drastically improve performance." This prompt ensures the AI gathers necessary context before attempting solutions, preventing the common "half-informed answer" problem.

## When to Use

- Debugging where you don't know the root cause yet
- Working in unfamiliar codebases
- When AI solutions keep missing something obvious

## Prompt

```
Before proposing any solution, complete this investigation:

## Context Gathering (Do this first)

1. **What files/code are directly involved?** List them. Read them.

2. **What's the expected behavior?** State it precisely.

3. **What's the actual behavior?** State it precisely.

4. **What changed recently?** Check git history, recent modifications.

5. **What assumptions are being made?** List them. Verify each one.

6. **What's the broader system context?** How does this component fit into the larger system?

## Checkpoint

After gathering context, summarize:
- Root cause hypothesis (with confidence level)
- What evidence supports this hypothesis
- What evidence would disprove it

WAIT for confirmation before proceeding to solution.
```

## Why It Works

From research: "Context ('additional information') is underrated—and massively impactful. Simply giving the model more relevant background can drastically improve performance."

The checkpoint prevents the AI from jumping to solutions based on incomplete understanding - a common failure mode.

## Example

Bad flow:
"My API returns 500 error" -> AI suggests generic error handling

Good flow:
"My API returns 500 error. Use context-first investigation."
-> AI reads the endpoint code, checks logs, examines middleware
-> Discovers: auth middleware throws when JWT_SECRET is missing in .env
-> Root cause identified before any fix attempted

## Notes

- The WAIT checkpoint is critical - it forces a pause for human validation
- Works exceptionally well with Claude Code's file reading capabilities
- Can be abbreviated for simpler issues: "Read the relevant files first. State what you found. Then propose a fix."
