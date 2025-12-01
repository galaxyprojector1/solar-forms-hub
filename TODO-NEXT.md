# TODO - Prochaines Améliorations Formulaires Solaires

## FAIT (Session 1er décembre 2025)

- [x] Créer les nouveaux dossiers (formulaires/, success-screens/, landing-pages/, versions-completes/)
- [x] Déplacer v1 à v10 dans `/versions-completes/`
- [x] Mettre à jour le hub avec catégories (PRO, Ultra Conversion, Animations, Classiques)
- [x] V11 - Clean Conversion (ultra épuré, style Apple)
- [x] V12 - Trust Builder (avis clients rotatifs, badges RGE, garanties)
- [x] V13 - Urgency (compteur temps réel, places limitées, FOMO)
- [x] V14 - Mobile Ultra (swipe navigation, 100% tactile)

---

## PROCHAINES TÂCHES

### 1. MODULES FORMULAIRES (dossier `/formulaires/`)

Extraire des formulaires SEULS (sans écran success) réutilisables :

- [ ] **f1-minimal** - Formulaire ultra simple (5 étapes, fond blanc)
- [ ] **f2-dark** - Formulaire dark mode élégant
- [ ] **f3-cards** - Formulaire avec sélection par cartes visuelles

> Ces formulaires doivent pouvoir rediriger vers N'IMPORTE QUEL success screen

---

### 2. MODULES SUCCESS SCREENS (dossier `/success-screens/`)

Extraire des écrans de fin SEULS réutilisables :

- [ ] **s1-simulation** - Compteur économies animé (style V10)
- [ ] **s2-confetti** - Explosion de confetti célébration
- [ ] **s3-gamification** - XP, badges, niveau atteint (style V8)
- [ ] **s4-simple** - Juste un check vert + message de confirmation

> Ces screens reçoivent les données du formulaire en paramètres URL

---

### 3. LANDING PAGES COMPLÈTES (dossier `/landing-pages/`)

Pages complètes prêtes à déployer :

- [ ] **lp1-hero-form** - Hero section + formulaire intégré + footer
- [ ] **lp2-testimonials** - Landing avec avis clients + formulaire
- [ ] **lp3-benefits** - Liste avantages solaire + formulaire

---

### 4. AMÉLIORATIONS VERSIONS EXISTANTES

- [ ] Ajouter compteur économies DÈS LE DÉBUT sur toutes les versions (comme V10)
- [ ] Tester toutes les versions sur mobile réel
- [ ] Optimiser le poids des fichiers (< 150KB chacun)

---

### 5. NOUVELLES VERSIONS PRO (si demandé)

- [ ] V15 - Quiz interactif (questions fun avant le formulaire)
- [ ] V16 - Chatbot (formulaire style conversation)
- [ ] V17 - Video background (hero vidéo solaire)

---

## STRUCTURE ACTUELLE

```
solar-forms-hub/
├── index.html                    ← Hub principal (MIS À JOUR)
├── formulaires/                  ← VIDE (à remplir)
├── success-screens/              ← VIDE (à remplir)
├── landing-pages/                ← VIDE (à remplir)
└── versions-completes/
    ├── v1-neon/
    ├── v2-nature/
    ├── v3-glass/
    ├── v4-minimal/
    ├── v5-particles/
    ├── v6-morphing/
    ├── v7-3d/
    ├── v8-gamification/
    ├── v9-story/
    ├── v10-simulation/
    ├── v11-clean/                ← NEW
    ├── v12-trust/                ← NEW
    ├── v13-urgency/              ← NEW
    └── v14-mobile/               ← NEW
```

---

## CONTRAINTES TECHNIQUES (RAPPEL)

```
✅ Fichier unique HTML (pas de dépendances locales)
✅ CDN uniquement pour les librairies
✅ Mobile first (priorité)
✅ Compatible desktop
✅ Léger < 200KB
✅ Fonctionne en iframe
✅ Touch-friendly
✅ Compteur économies visible DÈS LE DÉBUT
```

---

## RÈGLE IMPORTANTE POUR L'AGENT

**TOUJOURS** après création/modification de fichiers :

```bash
git add .
git commit -m "description"
git push
vercel --prod --yes   # si le déploiement auto ne marche pas
```

**NE JAMAIS** dire "c'est terminé" sans avoir vérifié que c'est VISIBLE sur Vercel !

---

*Mis à jour le 1er décembre 2025*
