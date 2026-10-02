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

## Commit Standards

Format: `type(scope): subject`

- Subject: imperative, lowercase, no trailing period, ≤ 72 chars
- Types: `docs`, `feat`, `fix`, `style`, `chore`, `revert`
- Scope: `profile`, `brand`, `deps`

Examples:
- `docs(profile): update project list`
- `feat(brand): add new logo variants`
- `chore(deps): update oxfmt`
