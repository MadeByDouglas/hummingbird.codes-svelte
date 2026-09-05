# Hummingbird website

Svelte 5 / SvelteKit site for hummingbird.codes with static generation, TypeScript, Tailwind 3 and custom shared components.

## Development

- `npm run dev`, `npm run build`, `npm run preview` start development, generate `build/`, and preview it.
- `npm run check` synchronizes SvelteKit and runs `svelte-check`; `npm run lint` runs ESLint. `typecheck` runs the same type checker without the sync step, so do not run both checks redundantly unless needed.
- Consult current Svelte documentation for unfamiliar APIs. Use available documentation tools when useful; no particular MCP server or full documentation preload is required.

## Structure and contracts

- `src/lib/components/` owns shared header, footer, hero and UI components. Reuse these and the Tailwind theme rather than introducing a second UI system.
- `content/` owns YAML data and Markdown snippets; `src/lib/content.ts` loads local files. Preserve content types and existing Markdown rendering when editing content flows.
- `src/routes/` defines pages and loaders, including docs/Discord redirects. Preserve `BASE_PATH` handling in `svelte.config.js` and the static adapter/prerender setup.
- Static assets live in `static/`, not `public/`. `src/app.css` and `tailwind.config.ts` define styling; retain the orange/zinc palette, light/dark behavior and shared rounded controls.
- Existing Iconify collections and Shiki/Markdown handling cover icons and code content. Inspect current configuration for supported syntax instead of maintaining a duplicate language list here.
