# SESSION SUIVANTE - Évolution Complète Formulaire

## ÉTAPE 1 : INSTALLER BMAD

```bash
cd C:\Users\yohann\Desktop\solar-forms-hub\solar-forms-hub
npx bmad-method@alpha install
```

---

## ÉTAPE 2 : PROMPT POUR NOUVELLE CONVERSATION

```
## PROJET

Formulaire de simulation d'aides à la rénovation énergétique (solaire, PAC, isolation).
- URL actuelle : https://solar-forms-hub.vercel.app/multi-sites/eligibilite-clone/formulaire.html
- Cible : propriétaires de maison en France

## OBJECTIF

Faire ÉVOLUER ce formulaire pour maximiser :
1. Le taux de complétion
2. La qualité des leads (informations collectées)
3. L'engagement utilisateur
4. La pertinence de la simulation

## ÉTAT ACTUEL (V1)

Le formulaire V1 fait :
- 6 écrans linéaires (logement → propriétaire → code postal → surface → travaux → contact)
- Clic = avance automatique
- Affiche les aides par travaux (PAC: 11k€, etc.)
- Confettis à la fin

Problèmes identifiés :
- Espace vide sur mobile (screenshots dans .playwright-mcp/)
- Pas de personnalisation selon la région
- L'utilisateur ne choisit pas SUR QUOI il veut être aidé
- Simulation trop basique (juste un total)

## ÉVOLUTIONS POSSIBLES À EXPLORER

### Parcours utilisateur
- Demander d'abord sur quelles AIDES ils veulent se renseigner (MaPrimeRénov, CEE, régionales...)
- Adapter le flow selon leurs réponses
- Ajouter des questions de qualification (revenus, situation, urgence du projet)

### Personnalisation régionale
- Détecter le département depuis le code postal
- Afficher les aides régionales spécifiques
- Zone climatique (H1/H2/H3) pour calculs plus précis

### Simulation avancée
- Calcul plus détaillé selon les barèmes 2025 (voir DONNEES-2025.md si existant)
- Fourchettes selon les revenus
- Cumul des aides (MPR + CEE + régional)
- Reste à charge estimé

### UX/Engagement
- Pré-cocher les travaux populaires
- Loaders avec messages contextuels
- Progression plus engageante
- Micro-animations

## OUTILS MCP DISPONIBLES

- **Playwright** : tester le rendu mobile (375px), prendre des screenshots
- **Vercel** : déployer
- **GitHub** : commit/push
- **Fal.ai** : générer des images (avec run_model, pas generate_image)
- **Perplexity** : rechercher des infos sur les aides 2025

## FICHIERS DU PROJET

```
multi-sites/eligibilite-clone/
├── formulaire.html      # Code actuel à faire évoluer
├── SIMULATION-SPEC.md   # Specs originales
├── docs/
│   ├── 1-analysis.md    # Analyse V1
│   ├── 2-prd.md         # PRD V1
│   ├── 3-ux-architecture.md
│   └── 4-next-iteration.md  # Notes d'amélioration
└── DONNEES-2025.md      # Barèmes officiels (si existe)
```

Screenshots mobile : `C:\Users\yohann\Desktop\solar-forms-hub\.playwright-mcp\formulaire-mobile-screen*.png`

## CE QUE JE VEUX

1. **Utilise BMAD** : Lance `*workflow-init` pour que le système multi-agents gère le projet
2. **Explore et propose** : Analyse le formulaire actuel, propose des évolutions majeures
3. **Sois ambitieux** : Je veux une vraie amélioration, pas juste des corrections CSS
4. **Teste** : Utilise Playwright pour valider sur mobile
5. **Déploie** : Push sur GitHub et déploie sur Vercel

## CONTRAINTES TECHNIQUES

- HTML/CSS/JS vanilla (pas de framework)
- Un seul fichier HTML
- Mobile-first (375px minimum)
- < 100KB
- Touch targets 48px minimum

LANCE *workflow-init ET PROPOSE-MOI UN PLAN D'ÉVOLUTION !
```

---

## RÉSUMÉ DES IDÉES D'ÉVOLUTION

| Aspect | Actuellement | Évolution possible |
|--------|--------------|-------------------|
| Parcours | Linéaire fixe | Adaptatif selon les réponses |
| Aides | Liste générique | Choix des aides à explorer |
| Régional | Rien | Aides départementales, zone climatique |
| Simulation | Total simple | Détail par aide, reste à charge |
| Qualification | Basique | Revenus, urgence, situation |
| Visuel | Statique | Images générées, animations |

## MCP DISPONIBLES

| MCP | Usage |
|-----|-------|
| Playwright | Tests mobile, screenshots avant/après |
| Vercel | Déploiement |
| GitHub | Versioning |
| Fal.ai | Génération d'images (familles, maisons, etc.) |
| Perplexity | Recherche sur les aides 2025, barèmes |
| Context7 | Documentation technique |
