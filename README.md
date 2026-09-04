# Vinext Boilerplate

A simple boilerplate for [Vinext](https://github.com/cloudflare/vinext) — Cloudflare's experimental Vite plugin that reimplements the Next.js API surface (App Router, RSC, Server Actions, middleware) so a Next.js-style app runs on Vite and deploys to Cloudflare Workers.

## What is Vinext?

Vinext is **not** a new framework — it's a Vite plugin that re-implements the public Next.js API (routing, `next/*` imports, App Router, Pages Router, SSR/RSC, Server Actions, middleware, ISR) on top of Vite's build pipeline. You write standard Next.js code (`app/`, `pages/`, `next.config.js` conventions), but it builds with Vite instead of the Next.js compiler, and deploys natively to Cloudflare Workers (with other targets via Nitro).

- Experimental / MIT-licensed, maintained by Cloudflare
- ~94% of the Next.js 16 API surface covered
- Faster builds, smaller bundles than stock Next.js
- Repo: https://github.com/cloudflare/vinext
- Docs: https://vinext.io/

## Stack

- Vinext (Next.js API on Vite)
- TypeScript
- App Router
- Tailwind CSS
- Cloudflare Workers (deploy target)

## Getting Started

Install dependencies:

```bash
pnpm install
```

Run the dev server:

```bash
pnpm dev
```

Build for production:

```bash
pnpm build
```

Run the production build locally:

```bash
pnpm start
```

Deploy to Cloudflare Workers:

```bash
npx @vinext/cloudflare deploy
```

You'll need to be authenticated with Cloudflare first (`wrangler login`, or set `CLOUDFLARE_API_TOKEN`).

## Project Structure

```
app/               # App Router routes (standard Next.js conventions)
public/            # Static assets
vite.config.ts     # Vite + vinext + @cloudflare/vite-plugin config
wrangler.jsonc     # Cloudflare Workers config
next.config.js     # Optional, standard Next.js config conventions
```

## Status

This boilerplate was scaffolded with the official `create-vinext-app` generator, targeting Cloudflare Workers. Vinext itself is experimental — expect gaps versus a full Next.js production app.
