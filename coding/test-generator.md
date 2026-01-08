# Test Generator

## Description

Generate meaningful unit tests that cover happy paths, edge cases, and error conditions. Produces tests that actually catch bugs, not just increase coverage.

## Prompt

```
Generate tests for this code:

## Code to Test

{{code}}

## Testing Framework

{{framework}}

---

## Test Generation Process

### 1. Identify What to Test

**Function/Component purpose:**
- What is the main responsibility?
- What are the inputs and outputs?

**Behaviors to test:**
- [ ] Happy path (normal usage)
- [ ] Edge cases (boundaries, empty values)
- [ ] Error conditions (invalid inputs, failures)
- [ ] Side effects (if any)

### 2. Generate Test Cases

For each behavior, create tests following this structure:

```
describe('[FunctionName]', () => {
  describe('when [condition]', () => {
    it('should [expected behavior]', () => {
      // Arrange - set up test data
      // Act - call the function
      // Assert - verify the result
    });
  });
});
```

### 3. Test Categories

**Happy Path Tests:**
- Normal inputs produce expected outputs
- Standard use cases work correctly

**Boundary Tests:**
- Empty arrays/strings/objects
- Single element collections
- Maximum/minimum values
- Zero, negative numbers (if applicable)

**Error Tests:**
- Invalid input types
- Missing required parameters
- Null/undefined handling
- Network/database failures (if applicable)

**State Tests (if stateful):**
- Initial state is correct
- State changes as expected
- State is not mutated unexpectedly

### 4. Mock Strategy

- What external dependencies need mocking?
- What's the mock implementation?
- Verify mock was called correctly

### 5. Output Format

Provide complete, runnable test file with:
- Imports
- Test setup/teardown if needed
- All test cases
- Clear test names that describe behavior
```

## Variables

- `{{code}}`: The function/component to test
- `{{framework}}`: e.g., "Jest", "Vitest", "Playwright", "pytest"

## Example

**Input:**
```typescript
function calculateDiscount(price: number, discountPercent: number): number {
  if (price < 0) throw new Error('Price cannot be negative');
  if (discountPercent < 0 || discountPercent > 100) {
    throw new Error('Discount must be between 0 and 100');
  }
  return price * (1 - discountPercent / 100);
}
```

**Output:**
```typescript
import { describe, it, expect } from 'vitest';
import { calculateDiscount } from './pricing';

describe('calculateDiscount', () => {
  describe('happy path', () => {
    it('should apply 10% discount correctly', () => {
      expect(calculateDiscount(100, 10)).toBe(90);
    });

    it('should apply 0% discount (no change)', () => {
      expect(calculateDiscount(100, 0)).toBe(100);
    });

    it('should apply 100% discount (free)', () => {
      expect(calculateDiscount(100, 100)).toBe(0);
    });
  });

  describe('edge cases', () => {
    it('should handle price of 0', () => {
      expect(calculateDiscount(0, 50)).toBe(0);
    });

    it('should handle decimal prices', () => {
      expect(calculateDiscount(99.99, 10)).toBeCloseTo(89.99);
    });
  });

  describe('error handling', () => {
    it('should throw for negative price', () => {
      expect(() => calculateDiscount(-10, 10)).toThrow('Price cannot be negative');
    });

    it('should throw for negative discount', () => {
      expect(() => calculateDiscount(100, -5)).toThrow('Discount must be between 0 and 100');
    });

    it('should throw for discount over 100', () => {
      expect(() => calculateDiscount(100, 150)).toThrow('Discount must be between 0 and 100');
    });
  });
});
```

## Notes

- Test behavior, not implementation
- One assertion per test when possible
- Test names should read like documentation
- Don't test third-party code
- Use realistic test data
