<p align="center">
  <img
    src="assets/image.jpg"
    alt="Thanos — a cosmic gauntlet representing code simplification"
    width="800"
  />
</p>

<h1 align="center">THANOS</h1>

<p align="center">
  <strong>Make half the code disappear.</strong>
</p>

<p align="center">
  Less code. Less complexity. Same or better quality.
</p>

<p align="center">
  <code>/snap</code> — Simplify code without sacrificing quality.
</p>


## Remove What Isn't Needed

Thanos is an open-source code simplification skill for AI coding agents.

It removes unnecessary complexity while preserving correctness, readability, security, and maintainability.

> Does this code actually need to exist?

## The Philosophy

**Make half the code disappear. Not half the quality.**

Thanos looks for code that adds complexity without adding value:

- Duplicate logic and unnecessary repetition
- Redundant conditions, variables, and intermediate steps
- Abstractions that make simple things harder to understand
- Unnecessary dependencies, configuration, and boilerplate
- Dead code that can be safely verified and removed

The goal isn't fewer lines at any cost. It's **less code to understand, test, debug, and maintain**.

## Meet `/snap`

`/snap` is Thanos's core simplification skill. Point it at a function, file, directory, or project, and it will inspect the code, identify unnecessary complexity, make focused improvements, and verify the result.

```text
/snap
/snap src/services/
/snap src/services/payment.py
/snap calculate_total()
```

### How It Works

**01 — Inspect**

Understand the code's purpose, behavior, dependencies, contracts, and existing tests.

**02 — Identify**

Find duplication, redundant logic, needless abstractions, and complexity that doesn't earn its place.

**03 — Simplify**

Make the smallest meaningful changes while preserving behavior and readability.

**04 — Verify**

Review the diff and run relevant tests, linting, or type checks when available.

**05 — Report**

Explain what changed, why it's simpler, which checks ran, and what remains unverified.

## Safety First

Simplification is never an excuse to weaken essential engineering safeguards.

Thanos preserves:

- Business rules and expected behavior
- Authentication, authorization, and security checks
- Input validation, error handling, and data integrity
- Tests, assertions, and compatibility requirements
- Essential logging, auditing, and observability

It avoids unrelated refactoring, destructive cleanup, and changes made merely to reduce line count. It reports verification honestly and leaves code unchanged when no safe improvement is justified.

## Design Principles

| Principle | What it means |
|---|---|
| **Simplicity** | Prefer the clearest solution that solves the actual problem. |
| **Correctness** | Preserve behavior and important contracts. |
| **Evidence** | Verify before removing code whose purpose is uncertain. |
| **Focused changes** | Simplify the target without rewriting unrelated code. |
| **Quality over metrics** | Fewer lines are useful only when the result is still good engineering. |

## Getting Started

Thanos is in early development, with Claude Code as the initial integration target.

The core skill is designed to remain portable so it can support other AI coding agents through lightweight integrations.

Installation instructions will be finalized as the initial plugin and workflow are validated.

## Roadmap

- [x] Define the philosophy and safety principles
- [x] Define the `/snap` workflow
- [ ] Finalize the Claude Code plugin and installation
- [ ] Test `/snap` against representative code examples
- [ ] Add evaluation cases for useful simplifications and unsafe reductions
- [ ] Document contribution and testing guidelines
- [ ] Explore integrations with additional coding agents

## Contributing

Thanos is being built around one simple question: **Can we make this simpler without making it worse?**

Ideas, test cases, feedback, and contributions that help answer that question are welcome.

## License

License to be announced.

---

<p align="center">
  <strong>Make unnecessary code disappear.</strong>
  <br />
  Never make essential engineering safeguards disappear.
</p>
