# Extended Thinking

> Force Claude to show its work before answering — dramatically improves accuracy on complex problems.

## When to Use

- Multi-step logical problems
- Math and calculations
- Complex coding tasks spanning multiple files
- Decisions with many variables
- When correctness matters more than speed

## Why It Works

By forcing the AI to "think aloud," you activate more sophisticated processing. Research shows AI performs significantly better on complex tasks when prompted to break down reasoning. It's like asking a student to show their work — the process catches errors.

Cognition AI reported an **18% increase** in planning performance with extended thinking enabled on Sonnet 4.5.

## The Prompt

### Basic (Zero-Shot CoT)

Add this to any complex question:

```
Think through this step by step before providing your answer.
```

Or simply:

```
Let's think step by step.
```

### Structured Extended Thinking

```
Before answering, work through this systematically:

1. UNDERSTAND: Restate the problem in your own words
2. IDENTIFY: What are the key variables and constraints?
3. EXPLORE: What are the possible approaches?
4. EVALUATE: What are the tradeoffs of each approach?
5. DECIDE: Which approach is best and why?
6. EXECUTE: Implement the solution
7. VERIFY: Check your work for errors

Show your reasoning for each step, then provide the final answer.
```

### For Technical Decisions

```
I need to decide: [DECISION]

Think through this like a senior engineer:

1. What are we optimizing for? (speed, cost, maintainability, etc.)
2. What are the realistic options?
3. For each option:
   - Pros
   - Cons  
   - Hidden costs
   - Long-term implications
4. What would you recommend and why?
5. What could go wrong with this recommendation?

Take your time. I'd rather have a thorough analysis than a fast one.
```

## Example

### Without Extended Thinking
```
Should we use PostgreSQL or MongoDB for our e-commerce app?
```
*Result: Generic pros/cons list, probably misses your specific needs*

### With Extended Thinking
```
Should we use PostgreSQL or MongoDB for our e-commerce app?

Before recommending, think through:
1. What data patterns does e-commerce typically have?
2. What are the query patterns (reads vs writes, joins, aggregations)?
3. What scale are we likely to hit in years 1, 3, 5?
4. What's our team's existing expertise?
5. What are the operational costs of each?

Show your reasoning, then recommend with confidence level.
```
*Result: Structured analysis that considers YOUR situation*

## Variations

### For Debugging
```
Debug this issue systematically:

1. What is the expected behavior?
2. What is the actual behavior?
3. What are possible causes? (List at least 5)
4. For each cause, how would we verify or rule it out?
5. What's the most likely cause based on the evidence?
6. What's the fix?

Think out loud as you work through this.
```

### For Code Review
```
Review this code thoroughly:

1. First, understand what the code is trying to do
2. Check for correctness — does it actually work?
3. Check for edge cases — what inputs would break it?
4. Check for security — any vulnerabilities?
5. Check for performance — any bottlenecks?
6. Check for maintainability — is it readable?

Document your thinking, then summarize findings.
```

## Pro Tips

1. **Ask for confidence levels** — "Rate your confidence 1-10"
2. **Request alternatives** — "What's another approach?"
3. **Enable uncertainty** — "Flag anything you're unsure about"
4. **Set expectations** — "Take your time, accuracy matters"

## Tradeoffs

| Pros | Cons |
|------|------|
| Much higher accuracy | Slower responses |
| Catches logical errors | Uses more tokens |
| Better for complex tasks | Overkill for simple queries |
| Shows reasoning chain | May over-complicate simple things |

## When to Skip

- Quick factual lookups
- Creative writing (can kill spontaneity)
- Time-sensitive tasks
- Simple transformations

## Effectiveness

| Task Type | Impact |
|-----------|--------|
| Complex reasoning | ⭐⭐⭐⭐⭐ |
| Math/calculations | ⭐⭐⭐⭐⭐ |
| Multi-file coding | ⭐⭐⭐⭐ |
| Architecture decisions | ⭐⭐⭐⭐ |
| Simple queries | ⭐ (overkill) |

---

*Based on Anthropic's Claude 4 announcement and Cognition AI benchmarks*
