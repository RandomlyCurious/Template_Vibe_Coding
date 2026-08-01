# Template repo — Vibe coding encadré (SDD + TDD)

## Boucle de travail (par feature)
1. `git switch -c feat/<nom>`
2. Copier `docs/specs/TEMPLATE.md` → `docs/specs/<nom>.md`, remplir avec l'agent, VALIDER toi-même.
3. Agent en plan mode : il propose le plan depuis la spec, tu valides.
4. RED : tests d'abord → commit `test: <nom> (red)`
5. GREEN : implémentation, tests intouchables → commit `feat: <nom>`
6. `git push` → PR → CI verte → relecture des fichiers sensibles → merge squash.
7. Migration BDD ? `supabase db diff -f <nom>` puis test sur `supabase db reset` AVANT push.

## Démarrer un nouveau projet depuis ce template
```bash
npm ci                              # stack déjà scaffoldée, lock commité
npx playwright install chromium     # une fois par machine
cp .env.example .env.local          # remplir les clés Supabase
git config core.hooksPath .githooks # activer le pre-commit
npm run dev
```
Puis : renommer `name` dans `package.json`, vider `docs/decisions.md`, et supprimer
les tests de fumée (`tests/smoke.test.tsx`, `e2e/smoke.spec.ts`) dès la première feature.

## Stack en place
Next 16 (App Router) · React 19 · TypeScript strict · Tailwind 4 · Vitest 4 + Testing Library ·
Playwright · ESLint 9 (flat config). Détails : [docs/architecture.md](docs/architecture.md).

## Commandes
| | |
|---|---|
| `npm run dev` | serveur de dev |
| `npm test` | Vitest (mode run) |
| `npm run test:e2e` | Playwright |
| `npm run typecheck` | `tsc --noEmit` |
| `npm run lint` | ESLint |
| `npm run build` | build de prod |

## Maintenance du template
Rafraîchir les versions ~tous les 6 mois : `npm outdated`, bump, relancer les 5 gates,
et vérifier que `npm audit --audit-level=critical` passe toujours.
