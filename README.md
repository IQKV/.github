## IQKV Foundation Project — GitHub Profile

A small workspace that powers the IQKV GitHub profile and provides optional developer tooling (commit hooks, formatting, and release helpers).

Use this repository to:

- **Maintain the organization profile**: content lives under `profile/` and renders on the GitHub org page.
- **Standardize commits and formatting**: via Husky, Commitlint, Prettier, Stylelint, and lint-staged.
- **Automate releases**: helpers are wired for conventional changelogs.

## Repository structure

- `profile/` — content for the org profile
  - `README.md` — main profile content
  - `Static-Analysis-and-Code-Quality-Guidelines.md` — quality rules and references
- `commitlint.config.js` — conventional commit rules
- `package.json` — tooling configuration (husky, lint-staged, prettier, etc.)

## Prerequisites

- Node.js ≥ 22.15.0
- Git

## Setup

Install dependencies (local dev tooling only):

```bash
npm install
```

Husky is configured via the `prepare` script and will auto-install hooks after `npm install`.

## Common scripts

```bash
# Run Stylelint over CSS files
npm run lint

# Check formatting with Prettier
npm run prettier:check

# Write formatting changes with Prettier
npm run prettier:write

# Remove local node_modules
npm run node_modules:clear
```

## Commit conventions

This repo uses **Conventional Commits** and enforces them with **Commitlint** and **Husky**.

- Recommended types: `feat`, `fix`, `docs`, `chore`, `refactor`, `test`, `build`, `ci`.
- Example: `feat(profile): add architecture overview section`

Optionally use Commitizen for guided commits:

```bash
npx cz
```

## Releasing

Changelog generation is configured for conventional commits. If you automate releases, use `release-it` or `semantic-release` according to your workflow. See `package.json` for available plugins.

## Editing the organization profile

Update the content in `profile/README.md`. GitHub will render this on the organization page. For code quality guidance referenced across projects, see:

- `profile/Static-Analysis-and-Code-Quality-Guidelines.md`

## License

Apache License 2.0 — see `LICENSE`.
