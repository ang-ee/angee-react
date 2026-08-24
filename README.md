# angee-react

The Angee framework's React packages — the composition root, transport, metadata
bridge, and rendered UI primitives that every Angee project and addon web
fragment composes:

- **`@angee/app`** — the composition root: routes, providers, addon manifests,
  the `angee-web-codegen` CLI, and the shared Vite/Vitest build config.
- **`@angee/refine`** — the Refine/Hasura transport, live updates, router, and
  typed-document glue.
- **`@angee/metadata`** — the `angee.resources` metadata bridge and projection.
- **`@angee/ui`** — the rendered binding, primitives, runtime context, and views.
- **`docs/`** — the Frontend Guidelines and end-to-end testing guide.
- **`storybook/`** — the storybook-first component workshop (dev-only).
- **`e2e/`** — the Playwright e2e harness (dev-only).

All four packages are schema-independent: they never import project-generated
GraphQL types. Addon web fragments live beside their Django code in the addon
repos, never here. Developed inside an Angee stack as a `sources:` checkout;
consumed by projects through the stack's pnpm workspace.

`AGENTS.md` is the agent/contributor entry point.
