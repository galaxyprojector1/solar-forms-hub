# BMAD - Installation et Utilisation Correcte

## PROBLÈME ACTUEL

BMAD est **partiellement installé**. Il manque le module `core/` qui contient :
- Le **party-mode** (orchestration multi-agents)
- Les 19 agents spécialisés complets
- Le moteur de collaboration

## INSTALLATION COMPLÈTE

```bash
cd C:\Users\yohann\Desktop\solar-forms-hub\solar-forms-hub
npx bmad-method@alpha install
```

Cela installera la structure complète :
```
.bmad/
├── core/                 ← MANQUANT - À installer
│   ├── workflows/
│   │   └── party-mode/   ← Orchestration multi-agents
│   └── tasks/
├── agents/               ← Présent (9 agents)
└── workflows/            ← Présent (34 workflows)
```

## COMMENT BMAD FONCTIONNE (MULTI-AGENTS)

### 1. Initialisation
```
*workflow-init
```
Cette commande analyse le projet et propose le bon parcours.

### 2. Party Mode (Multi-Agents)
Le party-mode permet de faire collaborer plusieurs agents :
- **John** (PM) : définit les requirements
- **Sally** (UX) : conçoit l'interface
- **Barry** (Dev) : implémente
- **TEA** : teste

### 3. Workflow Adaptatif
BMAD choisit automatiquement le niveau :
- **Level 0-1** : Quick Flow (bug fix, petite feature)
- **Level 2** : PRD + Architecture légère
- **Level 3-4** : Full Method (PRD + UX + Architecture + Epics)

## POUR LA PROCHAINE CONVERSATION

### Étape 1 : Installer BMAD complètement
```bash
npx bmad-method@alpha install
```

### Étape 2 : Initialiser le workflow
```
Charge l'agent PM (John) depuis .bmad/agents/pm.agent.yaml
Puis lance : *workflow-init
```

### Étape 3 : BMAD gère automatiquement
- Il détecte le projet existant (brownfield)
- Il propose le parcours adapté
- Il orchestre les agents nécessaires
- Il utilise les MCP disponibles (Playwright, Vercel, etc.)

## CE QUI VA CHANGER

| Avant (manuel) | Après (BMAD complet) |
|----------------|---------------------|
| Un seul agent à la fois | Multi-agents orchestrés |
| Prompts écrits à la main | Workflows automatiques |
| Pas de party-mode | Collaboration entre agents |
| MCP utilisés manuellement | MCP intégrés aux workflows |

## CONTEXTE PROJET POUR BMAD

Fichiers à référencer :
- `docs/4-next-iteration.md` : Améliorations demandées
- `formulaire.html` : Code actuel
- `.playwright-mcp/` : Screenshots mobile

Améliorations V2 :
1. Centrage vertical mobile
2. Loader après code postal + aides régionales
3. Pré-cochage travaux populaires
4. Infos détaillées sur les aides
