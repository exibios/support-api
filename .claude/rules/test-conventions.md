<!-- .claude/rules/test-conventions.md -->
---
paths:
  - "tests/**/*.py"
---

# Test conventions

pytest only. No unittest.TestCase, no self.assert* methods.

Fixtures go in conftest.py at the right level — project-wide in the root conftest,
module-specific fixtures in tests/routes/ or tests/services/ conftest files.

Before writing new tests, read the existing test file for that module first. Don't
suggest scenarios already covered.

Test function names describe what they verify:
  test_get_order_returns_404_when_order_not_found  ← good
  test_get_order_error                              ← too vague

When testing routes, mock at the service boundary — not the database directly.