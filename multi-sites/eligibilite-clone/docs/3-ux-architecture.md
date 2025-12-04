# Phase 3 - Architecture UX & Animations

## Structure Écran (Mobile 375px)

```
┌─────────────────────────────────┐
│  LOGO        [Progression 45%]  │  ← Header sticky
├─────────────────────────────────┤
│                                 │
│     Question principale         │  ← Titre 24px bold
│     Sous-texte explicatif       │  ← 14px gris
│                                 │
│  ┌─────────┐    ┌─────────┐    │
│  │  🏠     │    │  🏢     │    │  ← Cards 48% width
│  │ Maison  │    │  Appart │    │     Min 100px height
│  └─────────┘    └─────────┘    │
│                                 │
│  💡 "Plus de 15 000€ d'aides"  │  ← Badge motivant
│                                 │
└─────────────────────────────────┘
```

## Flow Détaillé

### Écran 1 : Type logement
- 2 cards côte à côte
- Clic → highlight + auto-avance (400ms delay)

### Écran 2 : Propriétaire
- 2 boutons full-width
- "Propriétaire" → continue
- "Locataire" → message "Demandez à votre propriétaire" + fin

### Écran 3 : Code postal
- Input centré, gros (font 24px)
- Validation temps réel (5 chiffres)
- Auto-avance dès valide

### Écran 4 : Surface
- Slider tactile avec valeur affichée
- Range : 30m² - 300m²
- Bouton "Valider" (exception au clic=avance)

### Écran 5 : Sélection travaux
- 3 cards principales (PAC, Isolation, Solaire)
- Chaque card : icône + nom + "Jusqu'à X€"
- Multi-sélection avec counter total
- Bouton "Voir mes aides" quand ≥1 sélectionné

### Écran 6 : Contact
- Progress bar à 92%
- 4 champs empilés
- Bouton "Recevoir mon estimation"
- Checkbox RGPD

### Écran 7 : Calcul
- Animation spinner 3 secondes
- Texte "Calcul de vos aides en cours..."
- Counter qui s'incrémente

### Écran 8 : Résultat
- Confettis
- Fourchette aides : "Entre X€ et Y€"
- "Un conseiller vous rappelle sous 24h"
- Liste travaux sélectionnés

## Animations CSS

```css
/* Ripple au clic */
.card::after { animation: ripple 0.6s ease-out; }

/* Slide entre écrans */
.screen-enter { animation: slideIn 0.4s ease; }

/* Counter animé */
.counter { animation: countUp 2s ease-out; }

/* Confettis */
.confetti { animation: fall 3s ease-in forwards; }
```

## Micro-interactions
- Hover cards : scale(1.02) + shadow
- Focus inputs : border-blue + glow
- Validation : checkmark vert animé
- Erreur : shake + border rouge
