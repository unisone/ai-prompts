# Expert Code Review

## Description

A systematic code review prompt that catches real issues instead of nitpicking style. Based on what senior engineers actually look for.

## When to Use

- Before merging PRs
- Self-review before pushing
- Learning from your own code
- Auditing unfamiliar codebases

## Prompt

```
Review this code as a senior engineer who's seen production outages.

**Focus on (in priority order):**

1. **Correctness Bugs**
   - Logic errors, off-by-one, null handling
   - Race conditions, state management issues
   - Incorrect assumptions about inputs

2. **Security Issues**
   - Injection vulnerabilities (SQL, XSS, command)
   - Auth/authz bypasses
   - Sensitive data exposure
   - Insecure defaults

3. **Reliability Risks**
   - Missing error handling
   - Unbounded operations (memory, time)
   - Network failure handling
   - Resource leaks

4. **Performance Problems**
   - N+1 queries
   - Unnecessary computation in hot paths
   - Memory allocation issues
   - Missing indexes (if DB)

5. **Maintainability**
   - Unclear naming or intent
   - Missing types or contracts
   - Overly complex logic
   - Duplicated code

**Output Format:**

🔴 **CRITICAL** - Must fix before merge
🟡 **WARNING** - Should fix, real risk
🟢 **SUGGESTION** - Nice to have
💭 **QUESTION** - Need clarification

For each issue:
- Location (file:line)
- Problem description
- Why it matters
- Suggested fix

**Skip:**
- Style preferences covered by linters
- Theoretical issues that won't happen
- "I would have done it differently" comments

[Paste code below]
```

## Why It Works

1. **Priority ordering**: Catches what actually causes outages
2. **Severity levels**: Makes it clear what's blocking
3. **"Why it matters"**: Educates, doesn't just criticize
4. **Skip list**: Avoids bikeshedding

## Streamlined Version

For quick reviews:

```
Review this code. Only flag:
1. Bugs or incorrect behavior
2. Security vulnerabilities  
3. Will cause problems at scale

Skip style nitpicks. Show issue, location, fix.
```

## Example Output

```
🔴 CRITICAL - SQL Injection
📍 api/users.ts:45
The query interpolates user input directly:
`SELECT * FROM users WHERE id = ${userId}`
→ Use parameterized query: `db.query('SELECT * FROM users WHERE id = $1', [userId])`

🟡 WARNING - Missing error boundary
📍 components/Dashboard.tsx:12
API failure will crash the entire app.
→ Wrap in ErrorBoundary or add try/catch with fallback UI

🟢 SUGGESTION - Consider memoization
📍 hooks/useExpensiveCalc.ts:23
This recalculates on every render.
→ Wrap in useMemo with appropriate deps
```

## Notes

- Works best when you provide surrounding context
- Ask it to focus on specific areas if codebase is large
- Combine with actual PR diff for best results
