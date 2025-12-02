# PROMPT - Amélioration Eligibilite Clone

## Objectif
Améliorer https://solar-forms-hub.vercel.app/multi-sites/eligibilite-clone/ pour en faire une landing page de génération de leads ultra-performante.

## Fichier à modifier
`multi-sites/eligibilite-clone/index.html`

## Améliorations à faire

### 1. ANIMATIONS (priorité haute)
Ajouter des animations impressionnantes partout :
- Hero : texte qui apparaît mot par mot, image qui slide depuis la droite
- Compteurs animés (déjà fait, vérifier)
- Cartes travaux : effet hover 3D, scale + shadow
- Section aides : cartes qui arrivent en cascade
- Parallax léger sur les images de fond
- Boutons : pulse animation, ripple effect au clic
- Progress bar animée dans le formulaire
- Confetti ou celebration quand formulaire soumis
- Micro-interactions sur tous les éléments cliquables

### 2. FORMULAIRE COMPLET (priorité haute)
Remplacer la section "Vérifions ensemble si vous êtes éligibles" par un formulaire multi-étapes spectaculaire :

**Étape 1 - Type de projet**
- Pompe à chaleur
- Isolation (murs, combles, sols)
- Panneaux solaires
- Chaudière gaz condensation
- VMC
- Fenêtres / Portes
- Plusieurs travaux

**Étape 2 - Votre logement**
- Type : Maison / Appartement
- Vous êtes : Propriétaire occupant / Propriétaire bailleur / Locataire
- Année de construction : Avant 1975 / 1975-1990 / 1990-2005 / Après 2005
- Surface habitable : <50m² / 50-100m² / 100-150m² / >150m²

**Étape 3 - Chauffage actuel**
- Type : Électrique / Gaz / Fioul / Bois / Autre
- Facture annuelle énergie : <1000€ / 1000-2000€ / 2000-3000€ / >3000€

**Étape 4 - Situation fiscale**
- Nombre de personnes dans le foyer : 1 / 2 / 3 / 4 / 5+
- Revenu fiscal de référence :
  - Très modeste (<15k€)
  - Modeste (15-25k€)
  - Intermédiaire (25-40k€)
  - Supérieur (>40k€)

**Étape 5 - Vos coordonnées**
- Nom / Prénom
- Email
- Téléphone
- Code postal
- Checkbox : J'accepte d'être contacté

**Design du formulaire :**
- Progress bar en haut (étape 1/5, 2/5, etc.)
- Animations de transition entre étapes (slide left/right)
- Boutons radio stylisés avec icônes
- Validation en temps réel
- Récapitulatif avant envoi
- Animation de succès spectaculaire à la fin
- Estimation des aides affichée dynamiquement

### 3. RESPONSIVE MOBILE (priorité haute)
- Tester sur 375px (iPhone) et 390px (iPhone 14)
- Menu hamburger fonctionnel
- Formulaire full-screen sur mobile
- Touch-friendly (boutons 48px min)
- Swipe entre les étapes du formulaire
- Prendre des screenshots mobile avec Playwright

### 4. AMÉLIORATIONS VISUELLES
- Ajouter plus d'images IA si nécessaire
- Gradient animé sur le hero
- Glassmorphism sur certaines cartes
- Dark mode du header au scroll
- Sticky CTA sur mobile
- Trust badges animés

### 5. PERFORMANCE
- Lazy loading images
- Optimiser les animations (GPU accelerated)
- Preload des fonts

## Captures d'écran à prendre
Utiliser Playwright pour capturer :
1. Version mobile hero (375px)
2. Version mobile formulaire étape 1
3. Version mobile formulaire étape 5
4. Version desktop formulaire complet
5. Animation de succès

## Règles à suivre (CLAUDE.md)
- HTML/CSS/JS vanilla uniquement
- Tout dans un seul fichier HTML
- CDN : AOS, FontAwesome, Google Fonts
- Mobile-first
- < 200KB par fichier
- Mettre à jour le dashboard si besoin
- Commit + push + deploy sur Vercel

## Livrables attendus
1. `multi-sites/eligibilite-clone/index.html` mis à jour
2. Screenshots dans `.playwright-mcp/`
3. Mise à jour `IMAGES.md` si nouvelles images
4. Deploy sur Vercel
5. Test final sur https://solar-forms-hub.vercel.app/multi-sites/eligibilite-clone/

## Commandes utiles
```bash
# Deploy
git add . && git commit -m "description" && git push && npx vercel --prod --yes

# Générer image IA
mcp__fal-ai__run_model avec model_id: "fal-ai/flux/dev"
```
