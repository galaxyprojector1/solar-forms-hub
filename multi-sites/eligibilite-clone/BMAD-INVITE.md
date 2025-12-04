# INVITE BMAD - Test Méthodologie

## COPIE CE TEXTE DANS UNE NOUVELLE CONVERSATION CLAUDE :

---

Tu vas utiliser la **méthodologie BMAD** (Build More, Architect Dreams) pour transformer un formulaire de simulation en expérience exceptionnelle.

## ÉTAPE 0 - LECTURE OBLIGATOIRE

Lis ces fichiers AVANT toute action :

1. **SPECS BUSINESS** : `C:\Users\yohann\Desktop\solar-forms-hub\solar-forms-hub\multi-sites\eligibilite-clone\SIMULATION-SPEC.md`
2. **BMAD README** : `C:\Users\yohann\Desktop\solar-forms-hub\solar-forms-hub\.bmad\README.md`
3. **FORMULAIRE ACTUEL** : `C:\Users\yohann\Desktop\solar-forms-hub\solar-forms-hub\multi-sites\eligibilite-clone\formulaire.html`

## MÉTHODOLOGIE BMAD - 4 PHASES

### PHASE 1 : ANALYSE
**Agent** : Analyst
- Audite le formulaire actuel
- Identifie les points faibles UX
- Liste les améliorations possibles
- **Output** : Créer `docs/1-analysis.md` (MAX 50 lignes)

### PHASE 2 : PLANNING
**Agent** : PM (John)
- Crée le PRD basé sur SIMULATION-SPEC.md
- Définit les user stories prioritaires
- **Output** : Créer `docs/2-prd.md` (MAX 100 lignes)

### PHASE 3 : SOLUTIONING
**Agent** : UX Designer (Sally) + Architect
- Design du nouveau flow
- Spécifications animations
- Architecture technique
- **Output** : Créer `docs/3-ux-architecture.md` (MAX 100 lignes)

### PHASE 4 : IMPLEMENTATION
**Agent** : Developer (Amelia)
- Implémente le nouveau formulaire.html
- Suit les specs des phases précédentes
- Test mobile (375px viewport)
- **Output** : `formulaire.html` modifié

## RÈGLES CRITIQUES

### Optimisation Contexte
1. **Tous les outputs dans `docs/`** - Les agents lisent ces fichiers, pas la conversation
2. **Limites strictes** - Chaque doc a une limite de lignes MAX
3. **Pas de code dans les résumés** - Le code va dans les fichiers, pas dans la conversation
4. **Résumé par phase** - 3 lignes max entre chaque phase

### Qualité
1. **Mobile-first** - Base 375px, touch targets 48px
2. **Animations CSS** - Pas de JS pour les animations si possible
3. **Crédibilité** - Chiffres réalistes, fourchettes pas montants exacts
4. **Engagement** - Clic = avancer, pas de bouton "Suivant" ennuyeux

## DÉPLOIEMENT FINAL

Après Phase 4 :
```bash
cd "C:\Users\yohann\Desktop\solar-forms-hub\solar-forms-hub"
git add . && git commit -m "Simulation v2 BMAD - UX exceptionnelle" && git push && npx vercel --prod --yes
```

## OUTPUT FINAL ATTENDU

À la fin, retourne UNIQUEMENT :
```
✅ BMAD COMPLET

📁 Documents créés :
- docs/1-analysis.md
- docs/2-prd.md
- docs/3-ux-architecture.md

🚀 URL Production : [URL VERCEL]

📱 Changements majeurs :
- [Point 1]
- [Point 2]
- [Point 3]
```

## COMMENCE MAINTENANT

1. Lis SIMULATION-SPEC.md
2. Lis formulaire.html actuel
3. Lance Phase 1 (Analyse)

---
