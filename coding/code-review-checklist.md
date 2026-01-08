# Code Review Checklist

## Description

A systematic 10-point code review checklist covering logic errors, security vulnerabilities, performance issues, and edge cases. Use this to catch bugs before they reach production.

## When to Use

- Reviewing PRs before merge
- Self-reviewing your own code before committing
- Auditing existing code for issues
- Training junior developers on what to look for

## Prompt

```
Review this code using the following checklist. For each category, identify specific issues with line numbers.

## Checklist

### 1. Logic Errors
- [ ] Off-by-one errors in loops or array access
- [ ] Incorrect boolean logic (AND vs OR, negation errors)
- [ ] Missing null/undefined checks before property access
- [ ] Race conditions in async code
- [ ] Incorrect comparison operators (== vs ===, < vs <=)

### 2. Security Vulnerabilities
- [ ] SQL injection (string concatenation in queries)
- [ ] XSS (unescaped user input in HTML)
- [ ] CSRF (missing tokens on state-changing requests)
- [ ] Hardcoded secrets or credentials
- [ ] Insecure direct object references
- [ ] Missing input validation at boundaries

### 3. Performance Issues
- [ ] N+1 query patterns
- [ ] Missing database indexes for frequent queries
- [ ] Unnecessary re-renders in React components
- [ ] Large objects in memory without cleanup
- [ ] Synchronous operations that should be async

### 4. Error Handling
- [ ] Swallowed exceptions (empty catch blocks)
- [ ] Generic error messages hiding useful info
- [ ] Missing error boundaries in UI
- [ ] Unhandled promise rejections
- [ ] No retry logic for transient failures

### 5. Edge Cases
- [ ] Empty arrays/objects
- [ ] Null/undefined inputs
- [ ] Maximum/minimum values
- [ ] Unicode and special characters
- [ ] Timezone handling

### 6. Code Quality
- [ ] Functions doing too many things
- [ ] Magic numbers without constants
- [ ] Duplicated logic that should be extracted
- [ ] Misleading variable/function names
- [ ] Dead code that should be removed

### 7. API Contract
- [ ] Breaking changes to public interfaces
- [ ] Missing required fields in responses
- [ ] Inconsistent error response format
- [ ] Missing rate limiting
- [ ] No versioning strategy

### 8. Testing
- [ ] Critical paths without tests
- [ ] Tests that test implementation, not behavior
- [ ] Missing edge case tests
- [ ] Flaky tests that pass/fail randomly

### 9. Documentation
- [ ] Public APIs without JSDoc/docstrings
- [ ] Complex logic without comments
- [ ] Outdated README
- [ ] Missing changelog entries

### 10. Dependencies
- [ ] Known vulnerable packages
- [ ] Unnecessary dependencies
- [ ] Missing lock file updates
- [ ] Incompatible version constraints

## Output Format

For each issue found:
- Category: [1-10]
- Line: [number]
- Issue: [description]
- Fix: [suggested fix]
- Severity: [critical/high/medium/low]
```

## Why It Works

Systematic checklists reduce cognitive load and ensure consistent coverage. Research on code review effectiveness shows that structured approaches catch 60% more defects than ad-hoc reviews. The checklist externalizes the review criteria, preventing the "looks fine to me" problem.

## Example

Input: A login endpoint implementation

Output:
```
Category: 2 (Security)
Line: 47
Issue: Password comparison using == instead of timing-safe comparison
Fix: Use crypto.timingSafeEqual() to prevent timing attacks
Severity: critical

Category: 4 (Error Handling)  
Line: 62
Issue: Generic "Login failed" message for all error types
Fix: Log specific error server-side, return generic message to client
Severity: medium

Category: 8 (Testing)
Line: N/A
Issue: No test for rate limiting after failed attempts
Fix: Add test verifying lockout after 5 failed attempts
Severity: high
```

## Notes

- Adjust severity thresholds for your context (startup vs. regulated industry)
- Not every review needs all 10 categories - prioritize based on the change
- For large PRs, focus on critical paths first
