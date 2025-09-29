# Repository Guidelines

## Project Structure & Module Organization
- Source: `src/` (components, pages/routes, utils). Server code may live in `server/` or `api/`.
- Assets: `public/` (static files), `assets/` or `src/styles/` for images, fonts, and CSS.
- Tests: `tests/` or colocated `src/**/__tests__/`. Snapshots in `__snapshots__/`.
- Config: root-level files like `package.json`, `.eslintrc*`, `.prettierrc*`, `tsconfig.json`, and `.env*`.

## Build, Test, and Development Commands
- `npm run dev` (or `yarn dev`/`pnpm dev`): starts the local development server.
- `npm run build`: creates a production build into `dist/` or `.next/`.
- `npm test`: runs unit tests; use `npm test -- --watch` for watch mode.
- `npm run lint` / `npm run format`: lint and autoformat the codebase.
- `npm start`: serves the production build when applicable.

## Coding Style & Naming Conventions
- Indentation: 2 spaces; keep lines concise and readable.
- Language: TypeScript preferred if present; otherwise modern ES modules.
- Naming: PascalCase for React/Vue/Svelte components; camelCase for variables and functions; kebab-case for filenames (except Components).
- Imports: absolute or aliased paths if configured (`@/utils/...`); order std/lib → external → internal.
- Tools: ESLint + Prettier. Run `npm run lint` and `npm run format` before pushing.

## Testing Guidelines
- Framework: Jest or Vitest for unit tests; Playwright/Cypress for e2e if present.
- Location: `tests/**/*.test.[jt]s?(x)` or colocated `*.test.tsx`.
- Coverage: target ≥ 80% for changed code; add tests with new features/bugs.
- Run: `npm test` locally and ensure flakiness is addressed.

## Commit & Pull Request Guidelines
- Commits: Conventional Commits (e.g., `feat: add hero section`, `fix: handle null image`).
- Branches: `feature/<slug>`, `fix/<slug>`, `chore/<slug>`.
- PRs: clear description, linked issues (e.g., `Closes #123`), screenshots for UI, steps to test, and risk/rollback notes. Keep diffs focused.

## Security & Configuration Tips
- Secrets: never commit `.env*`. Use `.env.example` for required variables.
- Versions: follow `.nvmrc`/`.node-version` if present; match `engines` in `package.json`.

## Agent-Specific Notes
- Keep patches minimal and scoped. Do not reformat unrelated files.
- Preserve existing patterns and configs. Prefer existing scripts and directory conventions.
- Validate changes by running `npm run dev`, `npm test`, and `npm run build` locally.
