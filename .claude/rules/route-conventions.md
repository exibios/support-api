<!-- .claude/rules/route-conventions.md -->
---
paths:
  - "app/routes/**/*.py"
---

# Route handler conventions

Route handlers do exactly three things: validate input, call a service, return a response.
No business logic. No database queries.

Use the request object for input validation before passing anything to services.
Return responses using the helpers in app/responses.py.

Errors from services arrive as AppError — catch those in the handler and return the
appropriate HTTP response. Don't catch other exceptions; let them reach the error
handler middleware.