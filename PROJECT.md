# Sylphx Website

`website` is an active application repository for the Sylphx company website.
It owns the public marketing/content pages, Solid/Vite frontend, design-system
helpers, static assets, Vercel configuration, and static build workflow for the
company web presence.

## Lifecycle And Layer

- Lifecycle: `active`
- Layer: `application`

## Goals

- Present the Sylphx company website as a fast, maintainable, static frontend.
- Keep company pages, navigation, legal pages, design-system helpers, assets,
  build configuration, and deployment configuration coherent.
- Keep the website content-oriented and avoid hidden product/runtime coupling.

## Non-Goals

- Own backend product APIs, authentication, billing, customer data, or product
  runtime behavior.
- Own shared design doctrine, reusable frontend framework policy, or all
  Sylphx marketing content strategy outside this site.
- Publish enterprise doctrine, org rulesets, rollout issue reconciliation, or
  shared CI policy.

## Boundaries

This repository owns the public company website implementation. Product
systems, runtime APIs, auth, billing, and customer data stay in their owning
repositories. Shared packages such as `@sylphx/zen` are consumed through public
package exports only.

## Public Surfaces

- `src/pages/` defines public website pages.
- `src/components/`, `src/lib/design-system.ts`, and `src/stores/` define
  website-local UI behavior.
- `public/` defines static assets and web manifest.
- `package.json`, `vite.config.ts`, and `vercel.json` define build and deploy
  behavior.
- `.doctrine/project.json` is the machine-readable project manifest.

## Delivery

No repository-local CI workflow is currently present. Changes should be proven
with the relevant Bun, Vite, Biome, and static preview checks. Production proof
requires Vercel or hosting readback and a smoke of the affected public page.
The site is largely source-revertable because it is static and does not own
backend persistence.

The authoritative control-plane record is `.doctrine/project.json`.
