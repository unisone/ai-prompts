# XML Structured Prompts

> Claude 4.5's #1 technique — structure your prompts with XML tags for dramatically better results.

## When to Use

- Complex tasks with multiple components
- Long inputs (10,000+ tokens)
- When you need consistent, parseable output
- Multi-step workflows

## Why It Works

Claude 4.5 was trained on structured prompts internally. Anthropic's own system prompts use XML tags like `<behavior_instructions>`, `<artifacts_info>`, and `<knowledge_cutoff>`. By using the same structure, you're speaking Claude's native language.

## The Prompt

```xml
<task>
[What you want done - be specific]
</task>

<context>
[Background information, constraints, who this is for]
</context>

<input>
[The actual content to process - code, text, data]
</input>

<requirements>
- [Requirement 1]
- [Requirement 2]
- [Requirement 3]
</requirements>

<output_format>
[Exactly how you want the response structured]
</output_format>
```

## Example

### Before (unstructured)
```
Analyze this code for security vulnerabilities and performance issues. 
Focus on authentication flows and database queries. Provide specific 
recommendations with code examples.

[code here]
```

### After (XML structured)
```xml
<task>
Analyze the provided code for security vulnerabilities and performance bottlenecks
</task>

<focus_areas>
- Authentication flows
- Database query optimization
- Input validation
</focus_areas>

<code language="python">
[your code here]
</code>

<output_format>
For each issue found:
1. Location (file:line)
2. Severity (Critical/High/Medium/Low)
3. Description of the vulnerability
4. Corrected code example
5. Business impact
</output_format>
```

## Alternative Formats

XML isn't the only option. These work equally well:

### JSON
```json
{
  "task": "Review authentication code",
  "focus_areas": ["Password hashing", "Session security", "SQL injection"],
  "context": "Healthcare app, HIPAA required",
  "output_format": "Risk, impact, fix, severity per vulnerability"
}
```

### Clear Headers
```
TASK: Review authentication code for vulnerabilities

FOCUS: Password hashing, sessions, SQL injection

CONTEXT: Healthcare app requiring HIPAA compliance

OUTPUT FORMAT: Risk → HIPAA impact → Fix → Severity
```

## Pro Tips

1. **Nest for complexity** — Use nested tags for hierarchical requirements
2. **Name your tags semantically** — `<code>` is better than `<input1>`
3. **Keep tags consistent** — If you use `<requirements>`, don't switch to `<constraints>`
4. **Place long content in tags** — Helps Claude parse what's instruction vs. data

## When to Skip

- Simple questions ("What's the capital of France?")
- Casual conversation
- When you want Claude to use judgment on format

## Effectiveness

| Task Type | Impact |
|-----------|--------|
| Complex multi-part tasks | ⭐⭐⭐⭐⭐ |
| Code review/analysis | ⭐⭐⭐⭐⭐ |
| Document processing | ⭐⭐⭐⭐ |
| Simple queries | ⭐⭐ |

---

*Claude 4.5 optimized — tested December 2025*
