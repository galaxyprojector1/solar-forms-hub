# BMAD V2 - Amélioration Formulaire Simulation

## CONTEXTE
Le formulaire V1 a été déployé avec succès (clic=avance, aides affichées, confettis).
Cette itération V2 améliore l'UX mobile et ajoute de l'intelligence régionale.

## FICHIERS À LIRE AVANT TOUTE ACTION

1. **ÉTAT ACTUEL** : `formulaire.html` (V1 déployée)
2. **SPECS ORIGINALES** : `SIMULATION-SPEC.md`
3. **ANALYSE V1** : `docs/1-analysis.md`
4. **AMÉLIORATIONS V2** : `docs/4-next-iteration.md`
5. **SCREENSHOTS** : `.playwright-mcp/formulaire-mobile-screen*.png`

## MÉTHODOLOGIE BMAD - 4 PHASES

### PHASE 1 : AUDIT V1
- Lis `docs/4-next-iteration.md` pour comprendre les demandes
- Regarde les screenshots Playwright pour voir l'espace vide
- Output : Mettre à jour `docs/1-analysis.md` avec constats V2

### PHASE 2 : PRD V2
- Spécifier les 4 améliorations demandées
- Définir les données régionales nécessaires
- Output : Créer `docs/5-prd-v2.md` (MAX 80 lignes)

### PHASE 3 : DESIGN V2
- Mockup ASCII des nouveaux écrans
- Animations pour le loader régional
- Output : Créer `docs/6-ux-v2.md` (MAX 80 lignes)

### PHASE 4 : IMPLÉMENTATION
- Modifier `formulaire.html`
- Tester avec Playwright (375px)
- Déployer sur Vercel

## AMÉLIORATIONS DEMANDÉES (PRIORITÉ)

### P0 - Espace Mobile
Centrer verticalement le contenu dans la card blanche.
Les écrans 1-4 ont trop d'espace vide en bas sur mobile 375px.

### P1 - Loader Régional
Après code postal valide :
1. Afficher loader "Recherche des aides dans votre région..."
2. Pause 1.5-2 sec
3. Message "X aides régionales disponibles dans le [Département]"
4. Puis continuer vers surface

### P2 - Pré-cochage Travaux
Sur l'écran 5 (travaux), pré-cocher :
- Pompe à chaleur (11 000€)
- Isolation thermique (8 000€)
Total affiché dès l'arrivée : 19 000€

### P3 - Infos Aides
Avant l'écran travaux, afficher :
- Zone climatique (H1/H2/H3) basée sur code postal
- Liste des aides disponibles : MaPrimeRénov', CEE, régionales

## RÈGLES CRITIQUES
- Tous les outputs dans `docs/` (pas dans la conversation)
- Résumé 3 lignes max entre chaque phase
- Mobile-first, touch targets 48px minimum
- Utiliser Playwright MCP pour tester le rendu mobile
- Poids < 80KB

## OUTPUT FINAL
- URL Vercel avec formulaire V2
- 3 changements majeurs résumés
- Screenshots Playwright des nouveaux écrans

## COMMENCER
Lis `docs/4-next-iteration.md` puis lance Phase 1
