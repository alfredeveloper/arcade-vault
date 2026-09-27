# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

@AGENTS.md

## Project

Arcade Vault is a platform for playing games online and competing for the highest score. The repo is currently the Create Next App scaffold; no game or scoring code exists yet.

Development follows **Spec Driven Design** using the `/spec` and `/spec-impl` skills from [Klerith/fernando-skills](https://github.com/Klerith/fernando-skills) (install with `npx skills@latest add Klerith/fernando-skills`). Write a spec before implementing a feature. The README is in Spanish.

## Commands

- `npm run dev` — dev server at http://localhost:3000 (also regenerates the AGENTS.md block)
- `npm run build` — production build; also runs type checking
- `npm run start` — serve the production build
- `npm run lint` — ESLint 9 flat config (`eslint.config.mjs`, extends `next/core-web-vitals` + `next/typescript`)

No test framework is set up yet.

## Stack and conventions

- **Next.js 16.3 (App Router, `app/`) + React 19.2.** APIs differ from older Next versions. Check `node_modules/next/dist/docs/` (`01-app/` covers the App Router) before using a Next API, as AGENTS.md says.
- Layouts and pages use the global, auto-generated route type helpers (e.g. `LayoutProps<"/">`, `PageProps<...>`) with no import; their types are generated into `.next/types` and `.next/dev/types`.
- **Tailwind CSS v4** runs through `@tailwindcss/postcss`. There is no `tailwind.config.*`. Theme tokens are defined in `app/globals.css` through `@import "tailwindcss"` and an `@theme inline` block that maps CSS variables (`--background`, `--foreground`, and the Geist fonts from `next/font`) to Tailwind utilities.
- TypeScript is in strict mode. The path alias `@/*` maps to the repo root.
