# BMAD Specifications - Refonte Éligibilité V4

## 1. VISION PRODUIT

### Objectif Business
Maximiser les conversions (remplissage formulaire) en mettant les **AIDES FINANCIÈRES** au premier plan.

### Persona Principal
- **Âge** : 45-65 ans
- **Situation** : Propriétaire maison individuelle
- **Motivation** : Réduire factures énergie, améliorer confort
- **Freins** : Complexité administrative, peur des arnaques
- **Comportement** : Mobile principalement, attention limitée, besoin réassurance

### Proposition de valeur
"Découvrez en 2 minutes combien d'aides vous pouvez obtenir pour vos travaux"

---

## 2. ARCHITECTURE DES PAGES

### Page Index (Accueil) - PRIORITÉ 1
```
STRUCTURE :
├── Header (sticky, logo + CTA)
├── Hero Section
│   ├── Titre accrocheur avec montant max d'aides
│   ├── Sous-titre bénéfices
│   ├── CTA principal "Tester mon éligibilité"
│   ├── Trust badges (3-4 éléments)
│   └── Image hero (famille/maison)
├── Section "Vos aides disponibles"
│   ├── 3 cards cliquables (MPR, CEE, Régionales)
│   ├── Montants mis en avant (gros chiffres)
│   └── CTA secondaire
├── Section "Comment ça marche"
│   ├── 3 étapes visuelles
│   └── CTA inline
├── Section "Types de travaux"
│   ├── 4 cards (PAC, Isolation, Solaire, Fenêtres)
│   ├── Montant aide par travaux
│   └── Liens vers pages détail
├── Section Témoignages/Social Proof
│   ├── 2-3 témoignages avec montants obtenus
│   └── Compteur simulations réalisées
├── Section FAQ (3-4 questions)
├── CTA Final full-width
├── Footer
└── Sticky CTA Mobile (bottom)
```

### Pages Aides (MPR, CEE, Anah)
```
STRUCTURE :
├── Header
├── Hero avec logo aide officiel
├── Section "Montants par profil" (barèmes)
├── Section "Conditions d'éligibilité"
├── Section "Travaux éligibles" (liens)
├── Section "Cumul avec autres aides"
├── FAQ spécifique
├── CTA Final
└── Sticky CTA Mobile
```

### Pages Travaux (PAC, Isolation, Solaire)
```
STRUCTURE :
├── Header
├── Hero avec image travaux
├── Section "Combien d'aides pour ce travaux"
├── Section "Avantages" (économies, confort)
├── Section "Comment ça marche" (technique simplifié)
├── Section "Nos conseils"
├── CTA Final
└── Sticky CTA Mobile
```

---

## 3. DESIGN SYSTEM

### Couleurs
```css
:root {
    /* Primaires */
    --blue-dark: #1E3A8A;      /* Confiance, sérieux */
    --blue-primary: #2563EB;   /* Liens, accents */
    --orange: #F97316;         /* CTAs, urgence */
    --orange-dark: #EA580C;    /* Hover CTA */

    /* Succès/Argent */
    --green: #10B981;          /* Montants, succès */
    --green-light: #D1FAE5;    /* Backgrounds succès */

    /* Profils revenus */
    --bleu-mpr: #3B82F6;
    --jaune-mpr: #F59E0B;
    --violet-mpr: #8B5CF6;

    /* Neutres */
    --text-dark: #1F2937;
    --text-gray: #6B7280;
    --gray-light: #F3F4F6;
    --white: #FFFFFF;
}
```

### Typographie
```css
/* Titres Hero */
.hero-title {
    font-size: 2rem;      /* Mobile */
    font-size: 3.5rem;    /* Desktop */
    font-weight: 900;
    line-height: 1.1;
}

/* Titres Section */
.section-title {
    font-size: 1.75rem;   /* Mobile */
    font-size: 2.5rem;    /* Desktop */
    font-weight: 800;
}

/* Montants (gros chiffres) */
.amount-big {
    font-size: 2.5rem;    /* Mobile */
    font-size: 4rem;      /* Desktop */
    font-weight: 900;
    color: var(--green);
}

/* Corps */
body {
    font-size: 1rem;
    line-height: 1.6;
}
```

### Composants

#### CTA Principal
```css
.cta-primary {
    background: linear-gradient(135deg, var(--orange), var(--orange-dark));
    color: white;
    padding: 1.25rem 2rem;
    border-radius: 16px;
    font-size: 1.1rem;
    font-weight: 800;
    min-height: 60px;
    box-shadow: 0 8px 25px rgba(249, 115, 22, 0.35);
    transition: transform 0.2s, box-shadow 0.2s;
}

.cta-primary:hover {
    transform: translateY(-3px);
    box-shadow: 0 15px 40px rgba(249, 115, 22, 0.4);
}
```

#### Card Aide
```css
.aid-card {
    background: white;
    border-radius: 24px;
    padding: 2rem;
    box-shadow: 0 10px 40px rgba(0,0,0,0.08);
    transition: transform 0.3s, box-shadow 0.3s;
    cursor: pointer;
}

.aid-card:hover {
    transform: translateY(-8px);
    box-shadow: 0 20px 60px rgba(0,0,0,0.12);
}

.aid-card-amount {
    font-size: 2rem;
    font-weight: 900;
    color: var(--green);
}
```

#### Trust Badge
```css
.trust-badge {
    display: inline-flex;
    align-items: center;
    gap: 0.5rem;
    background: rgba(255,255,255,0.9);
    padding: 0.5rem 1rem;
    border-radius: 100px;
    font-size: 0.85rem;
    font-weight: 600;
}

.trust-badge i {
    color: var(--green);
}
```

#### Sticky CTA Mobile
```css
.sticky-cta {
    position: fixed;
    bottom: 0;
    left: 0;
    right: 0;
    background: linear-gradient(135deg, var(--blue-dark), var(--blue-primary));
    padding: 1rem;
    z-index: 1000;
    box-shadow: 0 -4px 20px rgba(0,0,0,0.15);
    display: none; /* Visible only on mobile */
}

@media (max-width: 768px) {
    .sticky-cta { display: block; }
}
```

---

## 4. INTERACTIONS & ANIMATIONS

### Scroll Reveal (AOS)
- Fade-up pour les cards
- Fade-right pour les étapes timeline
- Durée : 800ms
- Once: true (une seule fois)

### Hover Effects
- Cards : translateY(-8px) + box-shadow
- Boutons : translateY(-3px) + glow
- Liens : color transition

### Micro-interactions
- Haptic feedback sur CTAs (navigator.vibrate)
- Scale 0.98 sur click/touch
- Checkmark animation sur sélection

### Loading States
- Skeleton screens si données async
- Spinner pour transitions

---

## 5. CONTENU CLÉ

### Headlines à fort impact
- "Jusqu'à **25 000€** d'aides pour vos travaux"
- "**90%** des propriétaires sont éligibles"
- "Simulation **gratuite** en 2 minutes"
- "**15 847** simulations ce mois"

### Trust Elements
- "✓ 100% gratuit et sans engagement"
- "✓ Données officielles 2025"
- "✓ Artisans RGE certifiés"
- "✓ Accompagnement personnalisé"

### Social Proof
- Compteur simulations
- Témoignages avec montants réels
- Logos partenaires/labels

---

## 6. PERFORMANCE

### Objectifs
- First Contentful Paint < 1.5s
- Largest Contentful Paint < 2.5s
- Total page size < 100KB (hors images)
- Images optimisées WebP si possible

### Optimisations
- Fonts preconnect
- CSS inline critical
- Images lazy loading
- Scripts defer

---

## 7. ACCESSIBILITÉ

### WCAG 2.1 AA
- Contraste texte : 4.5:1 minimum
- Touch targets : 48px minimum
- Focus visible sur tous les éléments
- Support lecteur d'écran (aria-labels)
- Respect prefers-reduced-motion

---

## 8. CHECKLIST PRÉ-DEPLOY

- [ ] Mobile 375px : tous les éléments visibles
- [ ] CTAs : tous cliquables et visibles
- [ ] Images : toutes chargées
- [ ] Links : tous fonctionnels
- [ ] Forms : validation OK
- [ ] Animations : smooth, pas de jank
- [ ] Console : pas d'erreurs
- [ ] Lighthouse : score > 90
