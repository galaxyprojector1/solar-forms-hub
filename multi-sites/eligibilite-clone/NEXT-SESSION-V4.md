# Prochaine Session - Refonte index.html V4 COMPLÈTE

## ÉTAPE 0 - INSTALLER BMAD
```bash
npx bmad-method@alpha install
```

---

## PROBLÈMES ACTUELS À CORRIGER

### 1. Photos trop grosses
- Hero image prend trop de place sur mobile
- Images témoignages encore trop grandes (50px → 40px)
- Cards travaux : images disproportionnées

### 2. Espaces mal contrôlés
- Padding/margin incohérents entre sections
- Trop d'espace vertical gaspillé
- Sections trop longues sur mobile

### 3. Ergonomie mobile déficiente
- Scroll trop long pour arriver au CTA
- Informations clés pas assez condensées
- Touch targets à vérifier (48px min)

---

## SPECS DESIGN MOBILE-FIRST (375px)

### Règles strictes
```css
/* Espacement */
--section-padding: 40px 0;      /* PAS 80px */
--card-padding: 16px;           /* PAS 30px */
--gap-small: 12px;
--gap-medium: 20px;

/* Images */
--hero-img-height: 200px;       /* MAX sur mobile */
--avatar-size: 40px;            /* PAS 50-60px */
--card-img-height: 150px;       /* PAS 200px+ */

/* Typography */
--h1-mobile: 1.75rem;           /* PAS 3rem */
--h2-mobile: 1.5rem;
--body-mobile: 0.9rem;
```

### Structure Hero optimisée
```
┌─────────────────────────────┐
│ Badge "25 000€" (compact)   │
│ Titre H1 (2 lignes max)     │
│ Sous-titre (2 lignes max)   │
│ [CTA ORANGE PLEINE LARGEUR] │
│ Trust badges inline         │
└─────────────────────────────┘
Image hero APRÈS le CTA (ou supprimée)
```

### Structure Témoignages
```
Slider horizontal :
- Card width: 280px (pas 300px)
- Card height: auto (compact)
- Avatar: 40px
- Texte: 3 lignes max
- Pas de grandes photos
```

---

## WORKFLOW BMAD RECOMMANDÉ

### Phase 1 : Audit complet (10 min)
```
1. Ouvrir index.html sur mobile réel ou DevTools 375px
2. Mesurer chaque section (hauteur en px)
3. Identifier les "zones mortes" (espace gaspillé)
4. Lister les éléments à supprimer/réduire
```

### Phase 2 : Refonte CSS mobile-first (20 min)
```
1. Réécrire les media queries mobile
2. Réduire tous les paddings/margins
3. Contraindre les images (max-height)
4. Tester après CHAQUE changement
```

### Phase 3 : Validation Playwright (5 min)
```
1. Screenshot 375px
2. Mesurer : CTA visible en < 2 scrolls ?
3. Touch targets > 48px ?
4. Pas d'erreur console ?
```

---

## PROMPT POUR NOUVELLE SESSION

```
Lis NEXT-SESSION-V4.md et lance la refonte COMPLÈTE de index.html.

PROBLÈMES À CORRIGER :
1. Photos trop grosses → réduire drastiquement
2. Espaces mal contrôlés → padding 40px max par section
3. Ergonomie mobile → CTA visible rapidement

RÈGLES STRICTES :
- Mobile-first 375px
- Sections compactes (max 400px de hauteur chacune)
- Images contraintes (max-height)
- CTA visible en moins de 2 scrolls

WORKFLOW :
1. Audit avec mesures exactes
2. Refonte CSS section par section
3. Test Playwright après chaque section
4. Screenshot final de validation

NE PAS faire de sur-ingénierie. Garder simple et efficace.
```

---

## FICHIERS DE RÉFÉRENCE

| Fichier | Usage |
|---------|-------|
| `index.html` | Page à refondre |
| `BMAD-CONTEXT.md` | Contexte projet complet |
| `docs/BMAD-SPECS.md` | Design system |
| `images/` | 33 images disponibles |

---

## IMAGES IA GÉNÉRÉES (session actuelle)

Disponibles dans `images/` :
- `testimonial-couple-pac.jpg` (1024x576)
- `testimonial-famille-isolation.jpg` (1024x576)
- `artisan-solar-install.jpg` (1024x576)

---

## CE QUI A ÉTÉ FAIT (session actuelle)

### Améliorations
- Hero avec montants 25 000€ en vert
- Section Steps refaite en timeline verticale
- Témoignages en slider horizontal
- Sticky CTA amélioré avec compteur
- Données 2025 actualisées

### Problèmes non résolus
- Taille des images non contrainte
- Espaces verticaux trop importants
- Scroll trop long avant CTA
- Ergonomie globale à revoir

---

## OBJECTIF FINAL

Une page qui :
1. Affiche le CTA principal en < 2 scrolls sur mobile
2. A des sections compactes et bien espacées
3. Utilise des images optimisées (pas trop grandes)
4. Convertit efficacement (montants visibles, trust signals)

**Temps estimé : 30-45 min avec BMAD**
