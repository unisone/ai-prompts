# Safe Refactoring

## Description

A methodology for refactoring code without breaking functionality. Ensures changes are incremental, tested, and reversible.

## Prompt

```
I need to refactor this code. Guide me through a safe refactoring process.

## Current Code

{{current_code}}

## Refactoring Goal

{{goal}}

---

## Safe Refactoring Process

### Phase 1: Assessment

1. **Understand Current Behavior**
   - What does this code do? List all behaviors.
   - What are the inputs and outputs?
   - What side effects does it have?

2. **Identify Dependencies**
   - What calls this code?
   - What does this code call?
   - What would break if this code's interface changed?

3. **Check Test Coverage**
   - Are there existing tests? Do they pass?
   - What behaviors are NOT tested?
   - Can we add tests before refactoring?

### Phase 2: Safety Net

Before changing anything:

1. **Add characterization tests** - Tests that capture current behavior, even if it's buggy
2. **Identify invariants** - Things that must remain true after refactoring
3. **Create rollback plan** - How to undo if something goes wrong

### Phase 3: Incremental Changes

Refactor in small steps. After EACH step:
- [ ] Code compiles/runs
- [ ] All tests pass
- [ ] Behavior unchanged (unless intentionally changing it)
- [ ] Commit the change

**Refactoring Sequence:**

1. [First small change]
2. [Second small change]
3. ...

### Phase 4: Verification

1. **Run full test suite**
2. **Manual testing of critical paths**
3. **Compare before/after behavior**
4. **Review performance** - Did refactoring introduce slowdowns?

### Phase 5: Cleanup

1. Remove dead code
2. Update documentation
3. Update related tests
4. Notify affected team members
```

## Variables

- `{{current_code}}`: The code to refactor
- `{{goal}}`: What you want to achieve (e.g., "extract into reusable function", "simplify nested conditionals", "improve performance")

## Common Refactoring Patterns

| Pattern | When to Use |
|---------|-------------|
| **Extract Function** | Code block does one thing and is reused or too long |
| **Inline Function** | Function body is as clear as its name |
| **Extract Variable** | Complex expression needs a name |
| **Rename** | Name doesn't reflect purpose |
| **Move Function** | Function uses more from another module |
| **Split Loop** | Loop does multiple unrelated things |
| **Replace Conditional with Polymorphism** | Switch/if on type doing different behaviors |

## Example

**Goal:** Extract validation logic from a 50-line function

**Step 1:** Add tests for current validation behavior
**Step 2:** Extract validation into `validateInput()` function
**Step 3:** Replace inline validation with function call
**Step 4:** Verify tests still pass
**Step 5:** Add edge case tests for the new function

## Notes

- Never refactor and add features in the same commit
- If tests don't exist, write them first
- Small commits = easy rollback
- If a refactoring gets complicated, stop and break it into smaller steps
