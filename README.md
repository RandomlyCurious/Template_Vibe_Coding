# Template repo — Vibe coding encadré (SDD + TDD)

## Boucle de travail (par feature)
1. `git switch -c feat/<nom>`
2. Copier `docs/specs/TEMPLATE.md` → `docs/specs/<nom>.md`, remplir avec l'agent, VALIDER toi-même.
3. Agent en plan mode : il propose le plan depuis la spec, tu valides.
4. RED : tests d'abord → commit `test: <nom> (red)`
5. GREEN : implémentation, tests intouchables → commit `feat: <nom>`
6. `git push` → PR → CI verte → relecture des fichiers sensibles → merge squash.
7. Migration BDD ? `supabase db diff -f <nom>` puis test sur `supabase db reset` AVANT push.

## Installation
Voir la section "Mise en place" de la conversation ou docs/architecture.md.
