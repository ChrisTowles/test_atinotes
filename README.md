# test_atinotes

A testing ground for [AgentBoard](https://github.com/ChrisTowles/towles-tool) development. This repo uses a fork of [Atinotes](https://notes.atinux.com) — a Nuxt 3 + Nuxt UI Pro note-taking app — as a real-world codebase to validate AgentBoard card workflows, agent behaviors, and automation against.

## Why This Exists

AgentBoard cards need a realistic codebase to test against, not toy examples. This project provides that: a Nuxt app with routes, components, server APIs, and a real dependency graph. Cards are developed and validated here before being considered stable in [towles-tool](https://github.com/ChrisTowles/towles-tool).

## Tech Stack

- **Nuxt 3** with Nuxt UI Pro
- **NuxtHub** (Cloudflare deployment)
- **pnpm** package manager

## Quick Start

```bash
# Install dependencies
pnpm install

# Copy env and configure
cp .env.example .env

# Start dev server at http://localhost:3000
pnpm dev
```

## Other Commands

```bash
pnpm build    # Production build
pnpm lint     # Lint with ESLint
```

## Related

- [towles-tool](https://github.com/ChrisTowles/towles-tool) — Main repo containing AgentBoard, CLI tools, and Claude Code plugin

## License

[MIT](./LICENSE)
