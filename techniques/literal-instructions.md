# Literal Instruction Format for Claude 4.x

## Description

Claude 4.x changed behavior significantly: it now "takes you literally and does exactly what you ask for, nothing more." This prompt format ensures you get complete solutions by being explicit about the "above and beyond" behavior you want.

## When to Use

- When Claude gives minimal responses that miss obvious related concerns
- When you want comprehensive solutions, not just literal answers
- Transitioning workflows from Claude 3.x

## Prompt Template

```
[Your request]

## Scope Expansion
In addition to the literal request above, also:
- Consider and address related edge cases
- Note any security implications
- Flag potential issues I haven't asked about
- Suggest improvements beyond the minimum solution

## Output Requirements
- Complete, working solution (not pseudocode unless requested)
- Include necessary imports and setup
- Handle common error cases
- If making assumptions, state them
```

## Why It Works

Anthropic explicitly stated: "Customers who desire the 'above and beyond' behavior might need to more explicitly request these behaviors."

Claude 3.x inferred intent and expanded on vague requests. Claude 4.x requires explicit instruction to do so.

## Example

Claude 3.x prompt: "Write a login function"
-> Would include rate limiting, secure comparison, session handling

Claude 4.x same prompt:
-> Returns minimal function that checks username/password

Claude 4.x with literal instruction format:
```
Write a login function.

## Scope Expansion
Also address: rate limiting, timing attacks, session security, input validation, logging.

## Output Requirements
Production-ready code with error handling.
```
-> Returns comprehensive implementation

## Notes

- Not always needed - sometimes literal is exactly what you want
- Use when you notice Claude giving "technically correct but incomplete" answers
- Can be stored in CLAUDE.md to apply globally
