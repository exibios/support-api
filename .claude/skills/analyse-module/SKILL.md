<!-- .claude/skills/analyse-module/SKILL.md -->
---
name: analyse-module
description: Analyse a Python module — what it does, its dependencies, and any issues. Returns a structured summary.
context: fork
allowed-tools: Read, Grep, Glob
argument-hint: "path to the module (e.g. app/services/order_service.py)"
---

Analyse the module at $ARGUMENTS.

Return a structured summary covering:

1. Purpose — what this module does in plain terms
2. Public interface — the functions and classes other modules actually use
3. Dependencies — what it imports (standard library, third-party, and internal)
4. Dependents — what imports this module (search the codebase for this)
5. Patterns — design patterns or conventions the module uses
6. Issues — tight coupling, missing error handling, unclear naming, anything that
   conflicts with the conventions in CLAUDE.md

Keep it concise. A developer reading this should understand the module well enough
to start making changes without needing to open the source file first.