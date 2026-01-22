# Concise Output Control

## Description

A common complaint: AI outputs are too verbose. This prompt template produces focused, actionable outputs without padding, caveats, or unnecessary explanation.

## When to Use

- Getting rambling responses when you need direct answers
- Code generation producing excessive comments
- Wanting bullet points instead of paragraphs

## Prompt Templates

### For Direct Answers
```
Answer in 1-2 sentences maximum. No caveats, no "it depends," no explanations unless I ask. Direct answer only.

[Your question]
```

### For Code
```
Code only. No explanations, no comments except for non-obvious logic. No import statements unless they're unusual. No usage examples.

[Your request]
```

### For Analysis
```
Bullet points only. Max 5 bullets. Each bullet max 15 words. Most important first.

[Your analysis request]
```

### For Decisions
```
State your recommendation in one sentence. Then list max 3 supporting reasons, one line each. No alternatives unless I ask.

[Your decision request]
```

## Why It Works

Research shows GPT and Claude both "overcompensate when instructions are vague." Explicit output constraints eliminate padding because the model has clear boundaries to work within.

Claude 4.x specifically "takes you literally and does exactly what you ask for" - so being explicit about brevity now works better than previous versions.

## Example

Without constraint:
"Could you explain the difference between let and const in JavaScript?"
-> 300 word response with history, examples, edge cases

With constraint:
"1-2 sentences. Difference between let and const in JavaScript."
-> "let allows reassignment, const doesn't. Both are block-scoped."

## Notes

- Pair with follow-up "expand on point 2" for progressive detail
- For code, you can always ask "add comments" as a separate step
- Being explicit about format is not rude - it's efficient
