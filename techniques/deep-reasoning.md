# Deep Reasoning Protocol

## Description

Forces the model into extended thinking mode for genuinely hard problems. Based on research showing that explicit reasoning scaffolding improves performance on complex tasks.

## When to Use

- Architecture decisions
- Debugging gnarly issues
- Tradeoff analysis
- Any problem where the first answer is probably wrong

## Prompt

```
This is a hard problem. Take your time.

Before answering, work through this reasoning protocol:

<think>
## 1. Problem Decomposition
What are the sub-problems here? Break it down.

## 2. Assumptions Check
What am I assuming? Which assumptions might be wrong?

## 3. Alternative Approaches
List at least 3 different ways to solve this. Include unconventional options.

## 4. Tradeoffs Analysis
For each approach:
- Pros
- Cons  
- Hidden risks
- When it would be the best choice

## 5. Edge Cases
What could go wrong? What inputs/scenarios break each approach?

## 6. Prior Art
How have others solved similar problems? What can we learn from them?

## 7. Recommendation
Based on the above, what's the best path forward and why?
</think>

Now give me your recommendation with confidence levels.
```

## Why It Works

1. **Explicit reasoning**: Forces thorough analysis instead of pattern-matching
2. **Multiple perspectives**: The "3 approaches" requirement prevents anchoring
3. **Risk awareness**: Edge cases and hidden risks surface potential issues
4. **Structured output**: Makes the reasoning auditable

## Condensed Version

For simpler problems:

```
Before answering:
1. What are 3 ways to approach this?
2. What could go wrong with each?
3. Which do you recommend and why?
```

## Example Use

Input:
```
We need to add real-time collaboration to our document editor. 
[Include deep reasoning prompt]
```

Output includes:
- Decomposition (sync, conflict resolution, presence, persistence)
- Approaches (OT, CRDT, last-write-wins)
- Tradeoff analysis for each
- Recommendation with rationale

## Extended Version for Critical Decisions

Add these sections for high-stakes decisions:

```
## 8. Reversibility
How hard is it to change course if this is wrong?

## 9. Second-Order Effects
What does this decision enable or prevent in the future?

## 10. Devil's Advocate
Argue against your recommendation. What would someone who disagrees say?
```

## Notes

- Increases response time significantly
- Worth it for decisions you'll live with
- Not needed for routine tasks
- Can be used with `thinking` mode in Claude for even deeper reasoning
