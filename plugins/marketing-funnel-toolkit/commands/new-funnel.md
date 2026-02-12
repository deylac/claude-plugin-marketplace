---
description: Lance le workflow complet de creation de funnel marketing pour une formation ou un coaching.
argument-hint: "[nom-du-projet]"
---

# Workflow : Nouveau Funnel Marketing

Lance le workflow complet de creation de funnel pour le projet $ARGUMENTS.

## Phase 0 : Verification du brief

1. Lis `docs/project-brief.md`. S'il n'existe pas ou est incomplet, pose ces questions :
   - Quel est ton produit/service ? (formation, coaching, info-produit)
   - Qui est ton client ideal ? (age, metier, situation, douleur principale)
   - Quel probleme concret resous-tu ?
   - Quel resultat specifique obtiennent tes clients ? En combien de temps ?
   - Quel est ton prix ou fourchette de prix ?
   - As-tu des temoignages ou resultats clients ?

2. Remplis `docs/project-brief.md` avec les reponses.
3. Verifie `docs/brand-guidelines.md`. S'il est vide, utilise `/brand-voice` pour le creer.

## Phase 1 : Recherche et positionnement

1. Utilise l'agent **researcher** pour analyser le marche.
   Prompt suggere : "Analyse le marche de [niche]. Concurrents, gaps, tendances."
   Sauvegarde : `research/market-analysis.md`

2. Utilise la skill `/positioning` pour trouver l'angle unique.
   Complete `docs/project-brief.md` avec le positionnement choisi.

3. Mets a jour `scratchpad.md` avec l'etat du projet.
4. **Suggere `/clear` avant la phase suivante.**

## Phase 2 : Copy de la landing page

1. Lis `docs/project-brief.md` et `docs/brand-guidelines.md`.
2. Utilise la skill `/direct-response-copy` pour rediger le copy.
   Sauvegarde : `output/landing-pages/main-copy.md`

3. Fais verifier par l'agent **reviewer**.
4. Applique les corrections si score < 48/60.
5. Mets a jour `scratchpad.md`.
6. **Suggere `/clear`.**

## Phase 3 : Lead magnet

1. Utilise la skill `/lead-magnet` pour generer 5 concepts.
2. Presente les 5 concepts a l'utilisateur pour choix.
3. Cree le lead magnet choisi.
   Sauvegarde : `output/lead-magnet/`

4. Mets a jour `scratchpad.md`.
5. **Suggere `/clear`.**

## Phase 4 : Sequence email

1. Utilise la skill `/email-sequences` pour creer la sequence de bienvenue (5 emails).
   Sauvegarde : `output/emails/`

2. Fais verifier par l'agent **reviewer**.
3. Mets a jour `scratchpad.md`.
4. **Suggere `/clear`.**

## Phase 5 : Contenu SEO

1. Utilise la skill `/seo-content` pour creer 3 articles.
   Sauvegarde : `output/content/`

2. Mets a jour `scratchpad.md` avec le statut final.

## Regles transversales

- Sauvegarder chaque livrable dans `output/` immediatement
- Mettre a jour `scratchpad.md` apres chaque phase
- Suggerer `/clear` entre chaque phase pour preserver le contexte
- Faire verifier les livrables importants par l'agent reviewer
- Ne JAMAIS essayer de faire 2 phases en une session
