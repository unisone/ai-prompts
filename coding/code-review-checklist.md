# Code Review Checklist

## Description

A systematic code review prompt that catches bugs, security issues, and maintainability problems. Returns structured feedback with severity levels and specific line references.

## Prompt

```
Review this code using the checklist below. For each issue found, specify:
- Severity: CRITICAL / HIGH / MEDIUM / LOW
- Line number or range
- What's wrong
- How to fix it

## Checklist

### 1. Logic Errors
- [ ] Off-by-one errors in loops or array access
- [ ] Incorrect boolean logic (AND vs OR, negation errors)
- [ ] Missing null/undefined checks before property access
- [ ] Race conditions in async code
- [ ] Incorrect error handling (swallowed errors, wrong catch blocks)

### 2. Security Vulnerabilities
- [ ] SQL injection (string concatenation in queries)
- [ ] XSS (unescaped user input in HTML)
- [ ] Hardcoded secrets, API keys, or passwords
- [ ] Missing authentication/authorization checks
- [ ] Insecure data exposure in logs or error messages
- [ ] CSRF vulnerabilities in state-changing operations

### 3. Performance Issues
- [ ] N+1 queries (database calls in loops)
- [ ] Missing pagination for large datasets
- [ ] Unnecessary re-renders (React) or recomputation
- [ ] Blocking operations that should be async
- [ ] Memory leaks (unclosed connections, event listeners)

### 4. Error Handling
- [ ] Empty catch blocks
- [ ] Generic error messages that hide root cause
- [ ] Missing try-catch around operations that can fail
- [ ] Errors not propagated correctly to callers

### 5. Code Quality
- [ ] Functions longer than 30 lines
- [ ] More than 3 levels of nesting
- [ ] Magic numbers or strings (should be constants)
- [ ] Duplicated code that should be extracted
- [ ] Misleading variable or function names

## Code to Review

{{code}}

## Output Format

Return findings grouped by severity, then provide:
1. Summary: X critical, Y high, Z medium, W low issues
2. Recommendation: APPROVE / APPROVE WITH COMMENTS / REQUEST CHANGES / BLOCK
```

## Variables

- `{{code}}`: The code to review (paste the full file or diff)

## Example Output

```
## CRITICAL (1)

**SQL Injection** - Line 45
```javascript
const query = `SELECT * FROM users WHERE id = ${userId}`;
```
Fix: Use parameterized queries:
```javascript
const query = 'SELECT * FROM users WHERE id = $1';
await db.query(query, [userId]);
```

## HIGH (2)

**Missing null check** - Line 23
...

---

Summary: 1 critical, 2 high, 3 medium, 1 low
Recommendation: REQUEST CHANGES (critical security issue must be fixed)
```

## Notes

- Works with any programming language
- Adjust checklist items based on your tech stack
- For large PRs, review file-by-file
- Combine with automated linting for best coverage
