# Spec : <nom de la feature>

> Statut : brouillon | validée | implémentée
> Date : YYYY-MM-DD

## Objectif (1-3 phrases)
Ce que l'utilisateur final peut faire après cette feature, et pourquoi.

## Périmètre
- INCLUS : ...
- EXCLU (ne PAS implémenter) : ...

## Contraintes
- Tables/colonnes Supabase touchées + policies RLS attendues
- Perfs attendues (ex : liste < 300ms, pagination obligatoire au-delà de 50 lignes)
- Pas de nouvelle dépendance sans justification

## Interfaces
- Routes/pages : ...
- Fonctions/endpoints : signature d'entrée → sortie
- Schéma BDD : migration nécessaire ? oui/non — si oui, décrire

## Critères d'acceptation (deviennent les tests)
- [ ] Étant donné <contexte>, quand <action>, alors <résultat>
- [ ] Cas d'erreur : <entrée invalide> → <comportement>
- [ ] Cas limite : ...

## Découpage en tickets
Découper la feature en tickets de 30 min à 2 h de travail max, chacun testable
et commitable indépendamment, ordonnés par dépendance :
- [ ] T1 — migration + RLS <table> (test : policies vérifiées)
- [ ] T2 — <fonction/endpoint> (test : critère X)
- [ ] T3 — <UI> (test : critère Y)
Un ticket = un cycle RED→GREEN→REFACTOR = 1-2 commits. Cocher au fur et à mesure.

## Hors périmètre découvert en cours de route
Toute idée, bug ou amélioration repérée PENDANT l'implémentation et absente
des critères ci-dessus : NE PAS l'implémenter. La noter ici, l'humain décidera
(nouveau ticket, nouvelle spec, ou poubelle) :
- ...

## Interdits spécifiques
Fichiers/zones du code à ne PAS toucher pendant cette feature.

## Definition of Done
- Tous les critères couverts par un test qui passe
- typecheck + lint verts, CI verte
- RLS vérifiée si table exposée
- `docs/decisions.md` mis à jour si décision d'archi prise
