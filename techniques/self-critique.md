# Self-Critique Before Finalizing

## Description

Research shows that asking models to critique their own answers before finalizing leads to significantly better outputs. This prompt implements a systematic self-review that catches errors, inconsistencies, and missed requirements.

## When to Use

- Before accepting any non-trivial AI output
- After code generation, before committing
- When accuracy matters more than speed

## Prompt

```
Before finalizing your response, perform this self-critique:

1. **Requirement Check**: List each requirement from the original request. Mark each as [MET] or [MISSED].

2. **Assumption Audit**: What assumptions did you make? Are any of these assumptions potentially wrong?

3. **Edge Cases**: What edge cases exist? How does your solution handle them?

4. **Contradiction Scan**: Does any part of your response contradict another part?

5. **Completeness**: What's missing that a thorough solution would include?

After completing this critique, revise your response to address any issues found. Show your critique, then provide the improved final answer.
```

## Why It Works

From prompt engineering research: "Asking a model to critique its own answer (self-criticism) can lead to smarter, more accurate outputs. These are especially valuable in agent-like settings where multi-step reasoning is required." - Sander Schulhoff, Learn Prompting

## Example Usage

Input:
```
Write a function to validate email addresses.

[Include the self-critique prompt above]
```

Output includes:
- Initial implementation
- Self-critique showing missed edge cases (plus sign handling, internationalized domains)
- Revised implementation addressing those gaps

## Notes

- Adds latency but dramatically improves first-attempt accuracy
- Particularly effective for code, analysis, and decision-making tasks
- Can be shortened to "Critique your response for errors before finalizing" for simpler tasks
