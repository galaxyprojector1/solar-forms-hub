# TODO - Prochaines Améliorations Formulaires Solaires

## FAIT (Session 1er décembre 2025 - Agent 1)

- [x] Structure dossiers créée
- [x] V1 à V10 déplacées dans `/versions-completes/`
- [x] V11 Clean, V12 Trust, V13 Urgency, V14 Mobile créées
- [x] Hub principal mis à jour

## FAIT (Session 1er décembre 2025 - Agent 2)

- [x] Recherche Perplexity effectuée (concurrents, aides 2025, bibliothèques JS)
- [x] Dossiers `/landing-pages/` créés avec sous-dossiers
- [x] Dossiers `/formulaires/` créés avec sous-dossiers

### DONNÉES RÉCUPÉRÉES (Perplexity - à utiliser) :

**Concurrents à copier :**
- HelloWatt : 3000+ chantiers, leader solaire résidentiel, prix 5990€ à 13190€
- Effy : 16 ans d'expérience, 100000 foyers/an, jusqu'à 1400€ économies/an
- SunVolt : 4 ans expertise, 3000 installations, garantie économies 10 ans

**Chiffres clés MaPrimeRénov 2025 :**
- PAC géothermique : jusqu'à 11000€ (bleu) / 9000€ (jaune) / 6000€ (violet)
- PAC air/eau : jusqu'à 5000€ (bleu) / 4000€ (jaune) / 3000€ (violet)
- Chauffe-eau solaire : jusqu'à 4000€ (bleu) / 3000€ (jaune) / 2000€ (violet)
- Chauffage solaire combiné : jusqu'à 10000€ (bleu) / 8000€ (jaune) / 4000€ (violet)
- Prime autoconsommation PV : 80€/kWc
- Cumul possible : MaPrimeRénov + CEE + TVA 5.5% + Éco-PTZ (jusqu'à 50000€)

**Bibliothèques JS validées (CDN) :**
```
GSAP - https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js
ScrollTrigger - https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/ScrollTrigger.min.js
CountUp.js - https://cdnjs.cloudflare.com/ajax/libs/countup.js/2.8.0/countUp.umd.js
Canvas Confetti - https://cdn.jsdelivr.net/npm/canvas-confetti@1.9.2/dist/confetti.browser.min.js
tsParticles - https://cdn.jsdelivr.net/npm/tsparticles@2.12.0/tsparticles.bundle.min.js
AOS - https://cdnjs.cloudflare.com/ajax/libs/aos/2.3.4/aos.css + aos.js
SweetAlert2 - https://cdn.jsdelivr.net/npm/sweetalert2@11
Swiper - https://cdn.jsdelivr.net/npm/swiper@11/swiper-bundle.min.js
```

---

## PROCHAINES TÂCHES (EN COURS)

### CIBLE : Propriétaires de maison en France
### OBJECTIF : MAXIMUM DE LEADS / CONVERSION (exagération autorisée !)

---

### 1. LANDING PAGES COMPLÈTES (dossier `/landing-pages/`)

Chaque landing page = Page complète ultra-persuasive

**À CRÉER :**
- [ ] **lp-panneaux-solaires/index.html** - Landing complète panneaux solaires PV ← PROCHAIN
- [ ] **lp-pompe-a-chaleur/index.html** - Landing complète PAC
- [ ] **lp-isolation-exterieure/index.html** - Landing complète ITE
- [ ] **lp-multi-travaux/index.html** - Landing avec les 3 activités au choix
- [ ] **lp-simulateur-aides/index.html** - Simulateur MaPrimeRénov / CEE / aides
- [ ] **`/landing-pages/index.html`** - Page de présentation de toutes les landing pages

---

### 2. FORMULAIRES (dossier `/formulaires/`)

**À CRÉER :**
- [ ] **f-panneaux-solaires/index.html** - Formulaire spécialisé solaire
- [ ] **f-pompe-a-chaleur/index.html** - Formulaire spécialisé PAC
- [ ] **f-isolation/index.html** - Formulaire spécialisé isolation
- [ ] **f-multi-travaux/index.html** - Formulaire multi-activités
- [ ] **f-simulateur-aides/index.html** - Simulateur aides (revenus, situation)
- [ ] **`/formulaires/index.html`** - Page de présentation de tous les formulaires

---

### 3. METTRE À JOUR LE HUB PRINCIPAL

- [ ] Lien "Landing Pages" → `/landing-pages/index.html`
- [ ] Lien "Formulaires" → `/formulaires/index.html`

---

## STRUCTURE ACTUELLE DU PROJET

```
solar-forms-hub/
├── hub.html                      ← Hub principal (à mettre à jour)
├── TODO-NEXT.md                  ← CE FICHIER
│
├── formulaires/                  ← DOSSIERS CRÉÉS (vides)
│   ├── f-panneaux-solaires/
│   ├── f-pompe-a-chaleur/
│   ├── f-isolation/
│   ├── f-multi-travaux/
│   └── f-simulateur-aides/
│
├── landing-pages/                ← DOSSIERS CRÉÉS (vides)
│   ├── lp-panneaux-solaires/
│   ├── lp-pompe-a-chaleur/
│   ├── lp-isolation-exterieure/
│   ├── lp-multi-travaux/
│   └── lp-simulateur-aides/
│
└── versions-completes/           ← V1 à V14 (FAIT)
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
    ├── v11-clean/                ← Style propre, minimaliste
    ├── v12-trust/
    ├── v13-urgency/
    └── v14-mobile/
```

---

## ÉLÉMENTS OBLIGATOIRES POUR CHAQUE LANDING PAGE

```
✅ Hero CHOC avec compteur économies animé DÈS LE CHARGEMENT
✅ Chiffres exagérés : "Jusqu'à 70% d'économies" / "Jusqu'à 90% financé"
✅ Aides détaillées : MaPrimeRénov (montants 2025), CEE, TVA 5.5%, Éco-PTZ
✅ Social proof : "32 personnes regardent cette page" (FOMO)
✅ Urgence : "Offre limitée", "X places restantes ce mois"
✅ Témoignages clients (prénoms, villes, photos placeholder)
✅ Badges confiance : RGE, Garantie 25 ans, 15000+ clients satisfaits
✅ Formulaire intégré avec barre de progression
✅ Animations GSAP + ScrollTrigger
✅ Confetti à la soumission
✅ Footer certifications
```

---

## CONTRAINTES TECHNIQUES

```
✅ Fichier unique HTML (tout en un)
✅ CDN uniquement (pas de fichiers locaux)
✅ Mobile first responsive
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
git commit -m "description claire"
git push

# VÉRIFIER sur Vercel que c'est visible AVANT de dire "terminé" !
# URL projet : voir .vercel/project.json pour l'ID

# SI FIN DE CONTEXTE → mettre à jour ce TODO + écrire prompt pour le suivant
```

---

## PROMPT POUR LE PROCHAIN AGENT

```
Lis le fichier TODO-NEXT.md dans le projet solar-forms-hub et continue les tâches.

CONTEXTE :
- Les dossiers sont créés mais VIDES
- La recherche Perplexity est faite (données dans le TODO)
- Prochaine tâche : créer lp-panneaux-solaires/index.html

IMPORTANT :
- Utilise les données Perplexity déjà récupérées dans ce fichier
- EXAGÈRE les chiffres et l'urgence pour maximiser les leads
- Utilise GSAP + CountUp + Confetti + AOS pour les animations
- Cible = propriétaires de maison en France
- Après chaque création : git add, commit, push
- Mets à jour ce TODO au fur et à mesure
- Ne dis JAMAIS "c'est terminé" sans avoir vérifié sur Vercel
- SI FIN DE CONTEXTE → mets à jour ce TODO + écris prompt suivant
```

---

*Mis à jour le 1er décembre 2025 - Agent 2*
