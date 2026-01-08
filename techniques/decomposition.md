# Task Decomposition for Complex Problems

## Description

Research shows decomposition - breaking problems into sub-problems - leads to better AI performance on complex tasks. This prompt forces structured breakdown before execution.

## When to Use

- Tasks involving multiple components or steps
- Problems where partial solutions can be validated independently
- When the AI keeps producing incomplete or wrong solutions

## Prompt

```
Before solving, decompose this problem:

## Step 1: Identify Components
List every distinct sub-problem that must be solved. Number each one.

## Step 2: Dependencies
For each sub-problem, list which other sub-problems it depends on. Draw the dependency graph.

## Step 3: Validation Criteria
For each sub-problem, define how we'll know it's solved correctly.

## Step 4: Execution Order
Based on dependencies, determine the order to solve sub-problems.

## Step 5: Solve Sequentially
Solve each sub-problem in order. After each, verify against its validation criteria before proceeding.

Show all steps, then provide the complete integrated solution.
```

## Why It Works

From research: "Asking a model to first break a problem into sub-problems (decomposition) can lead to smarter, more accurate outputs." Complex tasks fail because the model tries to hold everything in working memory at once. Decomposition externalizes the structure.

## Example

Task: "Build a user authentication system"

Decomposition reveals:
1. Password hashing (no deps) - validate: bcrypt with cost 12+
2. Session management (no deps) - validate: secure, httpOnly cookies
3. Login endpoint (deps: 1, 2) - validate: rate limiting, timing-safe comparison
4. Registration endpoint (deps: 1) - validate: email verification, input sanitization
5. Password reset (deps: 1, 2) - validate: time-limited tokens, single use

Execution order: 1 -> 2 -> 3, 4 (parallel) -> 5

## Notes

- Overhead pays off for tasks taking >5 minutes of AI time
- Dependency mapping catches architectural issues early
- Validation criteria prevent "looks done but isn't" situations
