# Web Calculator Constitution

## Core Principles

### I. Simplicity & YAGNI
Build the simplest thing that satisfies the spec; nothing beyond the spec is added. No dependency enters the project without a written justification in plan.md explaining why the standard library or a few lines of our own code would not do.

### II. Pure Logic Core
The calculation engine is a pure module: same inputs give the same outputs, with no side effects. It has zero imports from React, the DOM, or browser APIs (no window, no localStorage). Persistence and keyboard handling live in the UI layer only. eval() and expression-parsing packages are banned.

### III. Test-First for the Core
A failing unit test must exist before any engine code is written. Every edge case named in a spec gets its own test. Tests, lint, and build must all pass before a pull request is opened.

### IV. Accessible & Responsive by Default
Everything works with the keyboard alone. Controls have labels (icon-only controls have aria-label), focus is always visible, text contrast is at least 4.5:1, and the layout is usable at 375px width. All colours, spacing, radii, and font sizes come from design tokens.

### V. Change Tracking
Every commit that changes behaviour appends a dated line to CHANGELOG.md in the house format: "- YYYY-MM-DD `type` (scope)" followed by an indented description. Types: feat, fix, refactor, docs, config, ui, infra.

## Technology Constraints

No state-management library, no component library, no CSS framework, no backend, and no database. Every added dependency needs a line in plan.md saying why the standard library or a few lines of our own would not do. Reusable UI primitives (button, panel) are built once and reused; no copy-pasted styles.

## Development Workflow

Features follow the SpecKit order: specify, clarify, plan, tasks, analyze, implement. No application code is written before tasks.md exists. Each feature lives on its own branch created by SpecKit, with one commit per workflow step. A feature is merged to main only after tests, lint, and build pass and the app has been used manually; the next feature branches from the updated main.

## Governance

This constitution supersedes other practices. Every plan.md includes a Constitution Check naming which principles apply and how the plan complies. Amendments are made deliberately by re-running the constitution step, with the reason stated in the pull request.

**Version**: 1.0.0 | **Ratified**: 2026-11-23 | **Last Amended**: 2026-11-23