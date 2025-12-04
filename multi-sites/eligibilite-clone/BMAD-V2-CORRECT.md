# BMAD V2 - Utilisation Correcte du Système

## Comment BMAD Fonctionne

BMAD utilise des **agents** (personas) qui ont des **workflows** (processus).
Les fichiers sont dans `.bmad/agents/` et `.bmad/workflows/`.

## Pour Activer BMAD Correctement

### Option 1 : Charger l'agent manuellement
```
Lis et adopte le persona de l'agent dans :
.bmad/agents/quick-flow-solo-dev.agent.yaml

Puis exécute le workflow :
.bmad/workflows/bmad-quick-flow/quick-dev/workflow.yaml

Pour améliorer le formulaire avec les specs dans :
docs/4-next-iteration.md
```

### Option 2 : Charger l'agent UX Designer
```
Lis et adopte le persona de Sally (UX Designer) dans :
.bmad/agents/ux-designer.agent.yaml

Puis exécute le workflow create-ux-design :
.bmad/workflows/2-plan-workflows/create-ux-design/workflow.md
```

## Agents Disponibles

| Agent | Fichier | Rôle |
|-------|---------|------|
| Barry | quick-flow-solo-dev.agent.yaml | Dev rapide solo |
| Sally | ux-designer.agent.yaml | Design UX/UI |
| PM | pm.agent.yaml | Product Manager |
| Architect | architect.agent.yaml | Architecture technique |
| Dev | dev.agent.yaml | Développeur |
| TEA | tea.agent.yaml | Test Engineer |

## Workflows Clés

| Trigger | Workflow | Usage |
|---------|----------|-------|
| quick-dev | bmad-quick-flow/quick-dev/ | Implémentation rapide |
| create-tech-spec | bmad-quick-flow/create-tech-spec/ | Créer une spec |
| create-ux-design | 2-plan-workflows/create-ux-design/ | Design UX complet |
| prd | 2-plan-workflows/prd/ | Product Requirements |

## Prompt Recommandé pour V2

```
Tu vas utiliser le système BMAD.

1. Lis l'agent Barry dans .bmad/agents/quick-flow-solo-dev.agent.yaml
2. Adopte son persona et ses principes
3. Charge le workflow quick-dev dans .bmad/workflows/bmad-quick-flow/quick-dev/workflow.yaml
4. Exécute les instructions du workflow pour améliorer le formulaire

Contexte projet :
- Fichier à modifier : formulaire.html
- Améliorations demandées : docs/4-next-iteration.md
- Screenshots mobile : .playwright-mcp/formulaire-mobile-screen*.png

Objectif : Implémenter les 4 améliorations P0-P3 (centrage mobile, loader régional, pré-cochage, infos aides)
```

## Différence avec ce qu'on a fait

| Avant (incorrect) | Après (correct) |
|-------------------|-----------------|
| Prompt "maison" qui imite BMAD | Charger les vrais fichiers BMAD |
| 4 phases inventées | Workflows officiels BMAD |
| Pas de persona | Agent Barry ou Sally |
| Pas de checklist | Checklists BMAD intégrées |
