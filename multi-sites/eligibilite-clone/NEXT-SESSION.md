# COPIE CE PROMPT DANS UNE NOUVELLE CONVERSATION

```
## ÉTAPE 1 : INSTALLE BMAD

Exécute cette commande :
cd C:\Users\yohann\Desktop\solar-forms-hub\solar-forms-hub && npx bmad-method@alpha install

Attends que l'installation soit terminée, puis continue.

## ÉTAPE 2 : LANCE LE PROJET

### PROJET
Formulaire de simulation d'aides à la rénovation énergétique.
- URL : https://solar-forms-hub.vercel.app/multi-sites/eligibilite-clone/formulaire.html
- Code : multi-sites/eligibilite-clone/formulaire.html
- Cible : propriétaires de maison en France

### OBJECTIF
Faire ÉVOLUER ce formulaire pour maximiser :
1. Taux de complétion
2. Qualité des leads
3. Engagement utilisateur
4. Pertinence de la simulation

### ÉTAT ACTUEL (V1)
- 6 écrans linéaires (logement → propriétaire → code postal → surface → travaux → contact)
- Clic = avance automatique
- Aides affichées par travaux (PAC: 11k€, etc.)
- Confettis à la fin

Problèmes :
- Espace vide sur mobile (screenshots dans C:\Users\yohann\Desktop\solar-forms-hub\.playwright-mcp\)
- Pas de personnalisation régionale
- L'utilisateur ne choisit pas sur quelles AIDES il veut se renseigner
- Simulation trop basique

### ÉVOLUTIONS À EXPLORER
- Demander d'abord sur quelles AIDES ils veulent se renseigner (MaPrimeRénov, CEE, régionales...)
- Parcours adaptatif selon les réponses
- Détecter le département → aides régionales spécifiques
- Zone climatique H1/H2/H3 pour calculs précis
- Simulation détaillée : cumul MPR + CEE + régional, reste à charge
- Questions de qualification (revenus, urgence du projet)
- Pré-cocher travaux populaires
- Loaders contextuels, micro-animations

### MCP DISPONIBLES
- Playwright : tests mobile 375px, screenshots
- Vercel : déploiement
- GitHub : commit/push
- Fal.ai : générer images (utilise run_model avec fal-ai/flux/dev)
- Perplexity : recherche aides 2025, barèmes

### FICHIERS
- multi-sites/eligibilite-clone/formulaire.html (code actuel)
- multi-sites/eligibilite-clone/SIMULATION-SPEC.md (specs)
- multi-sites/eligibilite-clone/docs/ (analyses)

### CONTRAINTES
- HTML/CSS/JS vanilla, un seul fichier HTML
- Mobile-first 375px, < 100KB, touch targets 48px

### ACTION
Lance *workflow-init pour que BMAD orchestre les agents et propose un plan d'évolution ambitieux.
Utilise les MCP (Playwright pour tester, Perplexity pour rechercher les barèmes 2025, Fal.ai pour images si besoin).
Déploie sur Vercel quand c'est prêt.

GO !
```
