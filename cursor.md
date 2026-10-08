# Project Overview

This is a **Node.js** project built with **TypeScript** and **Next.js**.
All application code, tooling, and documentation should assume this stack.

## Tech Stack

| Layer | Choice |
| --- | --- |
| Runtime | Node.js |
| Language | TypeScript |
| Framework | Next.js (App Router) |
| UI | React (via Next.js) |
| Package manager | npm (unless the repo already uses pnpm or yarn) |

## Goals

- Build a type-safe web app on Next.js.
- Keep server and client code clearly separated.
- Prefer App Router conventions (`app/`) over the Pages Router (`pages/`).
- Use TypeScript strictly; avoid `any` unless there is a documented reason.

## Project Structure

Use this layout as the default:

```text
app/                 # Next.js App Router: pages, layouts, API routes
  layout.tsx
  page.tsx
  api/               # Route handlers (app/api/**/route.ts)
components/          # Reusable React components
lib/                 # Shared utilities, clients, helpers
public/              # Static assets
types/               # Shared TypeScript types
```

## TypeScript Conventions

- Write all new files in TypeScript (`.ts` / `.tsx`).
- Do not add JavaScript (`.js` / `.jsx`) source files.
- Enable and respect strict TypeScript settings.
- Prefer explicit types for public functions, API payloads, and component props.
- Colocate component-specific types next to the component; put shared types in `types/`.
- Use `import type` for type-only imports.

## Next.js Conventions

- Use the App Router.
- Server Components are the default. Add `"use client"` only when the component needs browser APIs, state, effects, or event handlers.
- Put page UI in `page.tsx` and shared chrome in `layout.tsx`.
- Use Route Handlers (`app/api/.../route.ts`) for backend endpoints in this app.
- Prefer Next.js data fetching patterns (`fetch` in Server Components, `revalidate`, `generateMetadata`) over ad-hoc client fetching when possible.
- Use `next/link` for internal navigation and `next/image` for images.
- Keep secrets in environment variables. Never expose server-only secrets to Client Components.

## Node.js / Runtime

- Target a current LTS Node.js version.
- Put server-only logic (filesystem, secrets, DB clients) in Server Components, Route Handlers, or `lib/` modules that are never imported by client code.
- Prefer ESM-style TypeScript imports consistent with Next.js.

## Coding Standards

- Keep components small and focused.
- Name files after their default export (`Button.tsx`, `getUser.ts`).
- Use named exports for utilities; default exports are fine for Next.js `page.tsx` / `layout.tsx`.
- Handle loading, empty, and error states for user-facing views.
- Validate external input at API boundaries.
- Do not commit `.env` files or credentials.

## Scripts

Typical scripts for this stack:

```json
{
  "scripts": {
    "dev": "next dev",
    "build": "next build",
    "start": "next start",
    "lint": "next lint",
    "typecheck": "tsc --noEmit"
  }
}
```

## Agent Instructions

When working in this repo:

1. Treat this as a TypeScript + Next.js (App Router) Node.js app.
2. Match existing file structure and naming before inventing new folders.
3. Prefer Server Components; only add client components when interactivity requires it.
4. Keep types accurate; do not weaken types to make code compile.
5. If scaffolding is needed, use Next.js + TypeScript defaults, not a Pages Router or plain JS setup.
