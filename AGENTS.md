# AI Agent Development Guide

## Project Overview

**github-profile** — GitHub profile repository. Contains `profile/README.md` rendered on the GitHub user/organization page and brand assets in `brand/`.

**Key characteristics:**

- No application code — Markdown and brand assets only
- Node.js tooling (pnpm + Husky) for commit hooks and formatting

## Execution Discipline

- Read the existing file before editing.
- No speculative additions — change only what is requested.
- After two identical failures, change approach.

## Security

- No credentials, personal contact details, or internal URLs in profile content.
- Never bypass `--no-verify` unless explicitly requested.

## AI Agent Guidelines

- **Ask before applying**: describe the change, wait for approval.
- **Approval phrases**: "Yes", "Proceed", "Apply", "Do it", "Looks good"
- Keep content factual and accurate. No auto-generated summary files.

## Evaluation

How we judge whether an agent task in this repository is actually done. Evaluation is evidence-based — a claim without the result is not a pass.

> This section starts minimal and grows with the repository. Add a gate only when a change type repeatedly slips through without it.

### Definition of done

A task is evaluated as done only when all of the following hold:

- Every gate required by the change type below is satisfied.
- The final report names what was changed and what was checked — per AI Agent Guidelines.
- Nothing required was skipped silently. Something that could not be checked is reported as a gap, never as a pass.

### Required gates by change type

| Change type                   | Required gates                                                          |
| ----------------------------- | ----------------------------------------------------------------------- |
| Any change                    | No build or test gate — Markdown and assets only                        |
| Profile README content        | Rendered preview checked before presenting a result                     |
| Brand asset added or replaced | File referenced from `profile/README.md`; dimensions and format checked |
| Wording-only edit             | No gate                                                                 |

### Ordering

Check the narrowest relevant item first, then the rest for the change type. On a problem, stop and report it rather than continuing on an unverified base (see Execution Discipline).

## Commit Standards

Format: `type(scope): subject`

- Subject: imperative, lowercase, no trailing period, ≤ 72 chars
- Types: `docs`, `feat`, `fix`, `style`, `chore`, `revert`
- Scope: `profile`, `brand`, `deps`

Examples:

- `docs(profile): update project list`
- `feat(brand): add new logo variants`
- `chore(deps): update oxfmt`
