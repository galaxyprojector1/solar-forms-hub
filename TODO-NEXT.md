# TODO - Prochaines Améliorations Formulaires Solaires

## FAIT (Session 1er décembre 2025)

- [x] Structure dossiers créée
- [x] V1 à V10 déplacées dans `/versions-completes/`
- [x] V11 Clean, V12 Trust, V13 Urgency, V14 Mobile créées
- [x] Hub principal mis à jour

---

## PROCHAINES TÂCHES

### CIBLE : Propriétaires de maison en France
### OBJECTIF : MAXIMUM DE LEADS / CONVERSION (exagération autorisée !)

---

### 1. LANDING PAGES COMPLÈTES (dossier `/landing-pages/`)

Chaque landing page = Page complète ultra-persuasive

**À CRÉER :**
- [ ] **lp-panneaux-solaires** - Landing complète panneaux solaires PV
- [ ] **lp-pompe-a-chaleur** - Landing complète PAC
- [ ] **lp-isolation-exterieure** - Landing complète ITE
- [ ] **lp-multi-travaux** - Landing avec les 3 activités au choix
- [ ] **lp-simulateur-aides** - Simulateur MaPrimeRénov / CEE / aides

- [ ] **`/landing-pages/index.html`** - Page de présentation de toutes les landing pages

**UTILISER PERPLEXITY POUR :**
- Rechercher les meilleurs sites concurrents (Effy, HelloWatt, Sonergia, etc.)
- S'inspirer de leurs arguments de vente
- Trouver les chiffres clés (économies, aides, etc.)
- Copier les meilleures pratiques de conversion

---

### 2. FORMULAIRES (dossier `/formulaires/`)

**À CRÉER :**
- [ ] **f-panneaux-solaires** - Formulaire spécialisé solaire
- [ ] **f-pompe-a-chaleur** - Formulaire spécialisé PAC
- [ ] **f-isolation** - Formulaire spécialisé isolation
- [ ] **f-multi-travaux** - Formulaire multi-activités
- [ ] **f-simulateur-aides** - Simulateur aides (revenus, situation)

- [ ] **`/formulaires/index.html`** - Page de présentation de tous les formulaires

---

### 3. METTRE À JOUR LE HUB PRINCIPAL

- [ ] Lien "Landing Pages" → `/landing-pages/index.html`
- [ ] Lien "Formulaires" → `/formulaires/index.html`

---

## BIBLIOTHÈQUES CDN À UTILISER

Rechercher et utiliser les meilleures bibliothèques pour :

```
✅ GSAP - Animations fluides
✅ Anime.js - Animations légères
✅ CountUp.js - Compteurs animés
✅ Canvas Confetti - Explosions confetti
✅ tsParticles - Particules de fond
✅ Three.js - Effets 3D (si besoin)
✅ Lottie - Animations vectorielles
✅ SweetAlert2 - Popups stylés
✅ Swiper - Carrousels touch
✅ AOS - Animations au scroll
```

**CHERCHER SUR PERPLEXITY** les nouvelles bibliothèques tendance pour :
- Animations de formulaires
- Effets visuels conversion
- Progress bars créatives
- Micro-interactions

---

## ÉLÉMENTS CLÉS LANDING PAGE (EXAGÉRATION MAX)

```
✅ Hero CHOC (chiffres impressionnants, urgence)
✅ Compteur économies animé DÈS LE DÉBUT
✅ "Jusqu'à 70% d'économies" / "Jusqu'à 90% financé par l'État"
✅ Aides : MaPrimeRénov, CEE, TVA 5.5%, Éco-PTZ
✅ Témoignages clients (avec photos, villes)
✅ Badges : RGE, Garantie 10-25 ans, 15000+ clients
✅ Urgence : "Offre limitée", "X places restantes"
✅ FOMO : "32 personnes regardent cette page"
✅ Formulaire intégré avec progression visible
✅ Footer confiance (mentions, certifications)
```

---

## STRUCTURE CIBLE

```
solar-forms-hub/
├── index.html                    ← Hub principal
│
├── formulaires/
│   ├── index.html                ← PAGE PRÉSENTATION FORMULAIRES
│   ├── f-panneaux-solaires/
│   ├── f-pompe-a-chaleur/
│   ├── f-isolation/
│   ├── f-multi-travaux/
│   └── f-simulateur-aides/
│
├── landing-pages/
│   ├── index.html                ← PAGE PRÉSENTATION LANDING PAGES
│   ├── lp-panneaux-solaires/
│   ├── lp-pompe-a-chaleur/
│   ├── lp-isolation-exterieure/
│   ├── lp-multi-travaux/
│   └── lp-simulateur-aides/
│
└── versions-completes/           ← V1 à V14 (FAIT)
```

---

## RECHERCHE PERPLEXITY À FAIRE

Avant de créer chaque landing page, rechercher :

```
1. "meilleur site devis panneaux solaires France"
2. "landing page pompe à chaleur conversion"
3. "simulateur aides rénovation énergétique"
4. "arguments vente isolation extérieure"
5. "chiffres économies PAC France 2024"
6. "MaPrimeRénov montants 2024 2025"
7. "meilleures bibliothèques JS animation formulaire"
8. "bibliothèques JavaScript landing page conversion"
```

S'inspirer de : Effy, HelloWatt, Sonergia, Engie, TotalEnergies, QuelleEnergie

---

## CONTRAINTES TECHNIQUES

```
✅ Fichier unique HTML
✅ CDN uniquement (pas de fichiers locaux)
✅ Mobile first
✅ < 200KB par fichier
✅ Touch-friendly
✅ EXAGÉRATION pour conversion max
✅ Cible : propriétaires maison France
```

---

## RÈGLE POUR L'AGENT

```bash
# TOUJOURS après modification :
git add .
git commit -m "description"
git push
vercel --prod --yes

# VÉRIFIER sur Vercel AVANT de dire "terminé" !
```

---

## PROMPT POUR LE PROCHAIN AGENT

```
Lis le fichier TODO-NEXT.md dans le projet solar-forms-hub et continue les tâches.

IMPORTANT :
- Utilise Perplexity pour rechercher les concurrents et les meilleures pratiques
- Cherche les bibliothèques JS/CSS qui vont améliorer les animations et conversions
- EXAGÈRE les chiffres et l'urgence pour maximiser les leads
- Cible = propriétaires de maison en France
- Après chaque création : git add, commit, push ET vérifier sur Vercel
- Ne dis JAMAIS "c'est terminé" sans avoir vérifié que c'est visible en ligne
```

---

*Mis à jour le 1er décembre 2025*
