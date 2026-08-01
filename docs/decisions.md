# Décisions d'architecture (1 ligne datée par décision)
- 2026-08-01 : Init du template. Stack Next.js + Supabase + Vitest + Playwright.
- 2026-08-01 : Stack scaffoldée dans le template (Next 16.2.12 / React 19.2.4 / Tailwind 4 / Vitest 4 / Playwright 1.62) + `package-lock.json` commité, pour que la CI soit verte dès le premier commit d'un nouveau projet. Contrepartie : versions à rafraîchir ~tous les 6 mois.
- 2026-08-01 : CI — gate `npm audit` bloquante sur `critical` au lieu de `high` : Next tire `postcss` et `sharp` avec des avis *high* dont le seul correctif proposé est un downgrade en Next 9. À réévaluer à chaque bump de Next.
- 2026-08-01 : Pas de `next/font/google` dans le layout — évite un appel réseau au build et une source de flakiness CI.
- 2026-08-01 : Tests unitaires dans `tests/` (Vitest + jsdom), e2e dans `e2e/` (Playwright). Playwright build et démarre l'app lui-même quand `CI=true`, `npm run dev` en local.
