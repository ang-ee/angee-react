# AGENTS.md

The Angee framework's React packages: `app/`, `ui/`, `refine/`, `metadata/`
(published surface), plus `docs/` (Frontend Guidelines and the E2E guide) and
the dev-only `storybook/` and `e2e/` workshops.
`tsconfig.base.json` + `vitest.shared.ts` at the root are the one owner of
build configuration; every package extends/imports them.

Rules of this repo:

- **Schema independence is an invariant.** No package may import
  project-generated GraphQL types (`@angee/gql/*`); the architecture
  guardrails test enforces layering (`app/src/architecture-guardrails.test.ts`)
  and must be updated deliberately on any package-edge change.
- Package layering: `refine` and `metadata` depend on nothing Angee;
  `ui` → `refine` + `metadata`; `app` → all three.
- Addon web fragments do NOT live here — they sit beside their Django code in
  the addon repos and consume these packages through the stack's workspace.
- The wider constitution (find the owner, compose don't re-implement, DRY)
  lives in the angee-django repo's `AGENTS.md` and cross-cutting docs; it governs
  here, while the frontend guidelines and E2E guide live in this repo's `docs/`.

Checks: `pnpm -r typecheck` and `pnpm -r test` from the root.
