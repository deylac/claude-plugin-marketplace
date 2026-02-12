---
name: orchestrator
description: |
  Chef de projet marketing. Aide a planifier, prioriser et sequencer le travail.
  Utiliser quand on ne sait pas par ou commencer, quand on demarre un nouveau projet,
  ou quand on veut un plan d'action structure.
  Triggers: par ou commencer, planifie, organise, prochaine etape, workflow, plan d'action.
---

# Orchestrator Marketing

## Objectif

Guider l'utilisateur dans la planification et le sequencement de ses projets marketing
pour la vente de formations, coaching et info-produits.

## Processus

### Etape 1 : Evaluer l'etat du projet

1. Lire `scratchpad.md` s'il existe (etat du projet entre sessions)
2. Lire `docs/project-brief.md` s'il existe (brief du projet)
3. Lister les fichiers dans `output/` (livrables existants)
4. Determiner ce qui est fait, en cours, et a faire

### Etape 2 : Proposer un plan en phases

Toujours structurer le travail en phases de 3-5 taches maximum.
Chaque phase doit etre realisable en une session Claude Code.

**Phases standard pour un funnel de formation :**

| Phase | Objectif | Skills/Agents | Livrable |
|-------|----------|---------------|----------|
| 1. Recherche | Comprendre le marche | Agent researcher | research/market-analysis.md |
| 2. Positionnement | Angle unique | /positioning | docs/project-brief.md complete |
| 3. Copy | Texte de conversion | /direct-response-copy | output/landing-pages/main-copy.md |
| 4. Lead Magnet | Aimant a leads | /lead-magnet | output/lead-magnet/ |
| 5. Emails | Sequence de nurturing | /email-sequences | output/emails/ |
| 6. SEO/Contenu | Trafic organique | /seo-content | output/content/ |

### Etape 3 : Donner des instructions claires

Pour chaque phase, fournir :
- Le prompt exact a utiliser
- Les skills ou agents a invoquer
- Le fichier de sortie attendu
- Rappeler de faire `/clear` entre les phases
- Rappeler de mettre a jour `scratchpad.md`

## Criteres de qualite

- Le plan est adapte au contexte specifique du projet (pas generique)
- Chaque phase a un livrable concret et un chemin de fichier
- Les dependances sont respectees (recherche avant copy, copy avant design)
- Le plan tient compte de ce qui existe deja dans output/

## Erreurs courantes a eviter

- Proposer de tout faire en une seule session (context rot garanti)
- Sauter la phase de recherche (source de contenu generique)
- Commencer par le design avant d'avoir le copy
- Oublier scratchpad.md pour la persistence entre sessions
- Proposer plus de 5 taches par phase
