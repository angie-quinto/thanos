---
name: snap
description: Automatically simplify code by removing unnecessary complexity, duplication, and boilerplate while preserving correctness, readability, security, and maintainability. Use when the user invokes /snap on a function, method, file, module, directory, project, or current working context.
---

# /snap — Thanos Code Minimization

## Philosophy

**Make half the code disappear.**

Thanos eliminates unnecessary code and complexity to make software simpler, more efficient, and easier to maintain.

The goal is not to write the fewest lines possible. The goal is to achieve the required behavior with the least unnecessary complexity.

**Less code. Less complexity. Same or better quality.**

## Usage

Accept an optional target:

- `/snap` — inspect the current project and identify the best opportunities for safe simplification.
- `/snap <function-or-method>` — simplify a specific function or method.
- `/snap <file>` — simplify a file.
- `/snap <module-or-directory>` — simplify a module or directory.
- `/snap <project>` — simplify a project within the accessible workspace.

Interpret the target using repository context. If the target is ambiguous, ask for clarification before making changes.

## Automatic Workflow

Execute all five steps automatically whenever `/snap` is invoked. Do not ask the user to repeat these instructions.

### 1. Inspect

- Identify the target and its surrounding implementation.
- Understand required behavior, callers, dependencies, and constraints.
- Inspect relevant tests and existing project conventions.
- Check the working tree and preserve unrelated user changes.
- Establish what must continue working after simplification.

### 2. Identify

Find opportunities to eliminate unnecessary complexity:

- Duplicated logic and repeated transformations.
- Redundant conditions, branches, and intermediate variables.
- Unnecessary abstractions, wrappers, classes, or interfaces.
- Avoidable dependencies and configuration.
- Existing functionality that could be reused.
- Dead or obsolete code whose lack of use can be established.

Prioritize meaningful improvements with low regression risk.

### 3. Simplify

- Make the smallest meaningful change that solves the problem.
- Prefer existing functionality and straightforward solutions over new abstractions.
- Preserve behavior, business rules, public contracts, and compatibility.
- Keep code readable; avoid clever tricks and cryptic one-liners.
- Avoid unrelated refactoring, formatting, and architectural changes.
- Do not introduce speculative features or dependencies.
- Never delete code solely to meet a percentage or line-count target.

If no meaningful, safe improvement exists, leave the code unchanged and explain why.

### 4. Verify

- Review the diff for unintended changes.
- Run relevant existing tests, linters, type checks, or other project checks.
- Add or update focused tests when needed.
- Check important edge cases, error paths, and data integrity.
- Preserve security controls, validation, authorization, and essential observability.
- Run broader checks when justified by the change's scope.

Never claim a check passed unless it was actually executed and passed.

If verification is blocked, explain what could not be tested and why.

Do not overwrite unrelated work or perform destructive operations without authorization.

### 5. Report

Summarize the result:

- **Target:** What was inspected.
- **Snapped:** What was removed or simplified.
- **Why:** Why the new implementation is simpler and remains correct.
- **Verification:** Which checks ran and their actual results.
- **Remaining risks:** What remains unverified or requires attention.

Report actual line-count reductions only when reliably measured. Fewer lines do not automatically mean better code.

## Safety Rules

Correctness comes before code reduction.

Never weaken or remove essential:

- Authentication, authorization, or security controls.
- Input validation, error handling, or data integrity.
- Business rules and required edge-case behavior.
- Tests, assertions, or compatibility guarantees.
- Privacy protections, audit requirements, or essential logging.

Do not perform broad rewrites, destructive cleanup, database changes, or public API changes merely to reduce code.

When a proposed change has significant uncertainty or regression risk, investigate further or ask for confirmation.

## Definition of Done

A snap is complete when:

1. The target and its required behavior are understood.
2. Every modification has a clear justification.
3. Unnecessary complexity is reduced without sacrificing quality.
4. The diff contains no unrelated changes.
5. Relevant checks have passed, or verification limitations are documented.
6. The user receives an honest summary of the changes and remaining risks.

**Final principle: Make unnecessary code disappear. Never make essential engineering safeguards disappear.**