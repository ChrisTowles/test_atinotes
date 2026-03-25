# Architecture

## Purpose

This repo is a sandbox for testing [AgentBoard](https://github.com/ctowles/towles-tool) card lifecycle workflows. It uses a fork of [Atinotes](https://notes.atinux.com) (a real Nuxt 3 note-taking app) so AgentBoard cards execute against a realistic codebase rather than toy examples.

### What gets tested here

- **Branch creation** — AgentBoard cards create feature branches (e.g. `agentboard/card-*`)
- **Agent execution** — Agents make real changes: editing components, adding API routes, modifying configs
- **PR creation** — Cards open pull requests against `main` via `gh pr create`
- **Merge flows** — PRs are rebase-merged back to `main` to validate the full card lifecycle

## Project Structure

```
test_atinotes/
├── app.vue                  # Root app component (NuxtPage + UNotifications)
├── app.config.ts            # Nuxt app config
├── nuxt.config.ts           # Nuxt 3 config (UI Pro, NuxtHub, auth, content, OG images)
├── pages/
│   └── [[slug]].vue         # Catch-all route — renders note pages by slug
├── components/
│   └── OgImage/
│       └── OgImagePage.vue  # OG image generation component
├── server/
│   ├── api/
│   │   ├── login.post.ts    # Auth endpoint
│   │   ├── pages.ts         # List pages
│   │   └── pages/
│   │       ├── [slug].get.ts  # Get page by slug
│   │       └── [slug].put.ts  # Update page by slug
│   └── routes/
│       └── assets/
│           └── [...pathname].get.ts  # Static asset serving
├── public/                  # Static assets
├── docs/                    # Project documentation
├── package.json             # pnpm workspace (atinotes)
└── nuxt.config.ts           # Modules: NuxtHub, UI Pro, Content, OG Image, Auth
```

## Tech Stack

| Layer       | Technology                          |
|-------------|-------------------------------------|
| Framework   | Nuxt 3                              |
| UI          | Nuxt UI + Nuxt UI Pro               |
| Content     | @nuxt/content (markdown pages)      |
| Auth        | nuxt-auth-utils                     |
| Storage     | NuxtHub KV (Cloudflare)             |
| Deploy      | Cloudflare (via wrangler + NuxtHub) |
| Package mgr | pnpm                                |

## Key Modules (nuxt.config.ts)

- `@nuxthub/core` — Cloudflare KV storage
- `@nuxt/ui` + `@nuxt/ui-pro` — Component library
- `@nuxt/content` — Markdown-driven pages
- `nuxt-auth-utils` — Session-based auth
- `nuxt-og-image` — Dynamic OG image generation
- `@nuxtjs/plausible` — Analytics

## Relation to towles-tool

The [towles-tool](https://github.com/ctowles/towles-tool) repo contains AgentBoard, the CLI, and the Claude Code plugin. This repo is a test target — AgentBoard cards point here to exercise their full lifecycle against real application code.
