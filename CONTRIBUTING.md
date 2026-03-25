# Contributing to test_atinotes

Thanks for your interest in contributing! This document covers the basics.

## Reporting Issues

Open a [GitHub issue](https://github.com/ctowles/test_atinotes/issues) with:

- A clear title and description
- Steps to reproduce the problem
- Expected vs actual behavior
- Node version, OS, and browser (if relevant)

## Submitting Pull Requests

1. Fork the repo and create a branch from `main` (see branch naming below).
2. Install dependencies with `pnpm install`.
3. Make your changes.
4. Run `pnpm lint` and fix any issues.
5. Test your changes locally with `pnpm dev`.
6. Open a PR against `main` with a clear description of what changed and why.

Keep PRs focused — one feature or fix per PR.

## Branch Naming

Use prefixed branch names:

- `feature/*` — new features (e.g., `feature/markdown-export`)
- `fix/*` — bug fixes (e.g., `fix/login-redirect`)

## Commit Message Format

Follow [Conventional Commits](https://www.conventionalcommits.org/):

```
<type>(<scope>): <description>
```

**Types:** `feat`, `fix`, `docs`, `style`, `refactor`, `test`, `chore`

Examples:

```
feat(notes): add markdown export
fix(auth): handle expired session redirect
docs: update contributing guide
```

Breaking changes: add `!` after the type/scope (e.g., `feat(api)!: change response format`).

## Coding Style

- **ES modules** — use `import`/`export`, not `require`.
- **Nuxt 3 conventions** — follow the standard Nuxt 3 project structure (`components/`, `pages/`, `server/`).
- **Linting** — run `pnpm lint` before committing. The ESLint config in `eslint.config.mjs` is the source of truth.
- **TypeScript** — use types where possible.

## Testing

- Verify changes work locally with `pnpm dev`.
- Run `pnpm build` to confirm nothing breaks the build.
- Run `pnpm lint` to catch style issues.

## License

By contributing, you agree that your contributions will be licensed under the [MIT License](./LICENSE).
