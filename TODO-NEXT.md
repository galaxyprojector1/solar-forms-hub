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

## FAIT (Session 1er décembre 2025 - Agent 3)

- [x] **lp-panneaux-solaires/index.html** - Landing solaire (orange, 1847€/an économies)
- [x] **lp-pompe-a-chaleur/index.html** - Landing PAC (bleu, 11000€ aides, comparaison chauffages)
- [x] **lp-isolation-exterieure/index.html** - Landing ITE (vert, 75€/m², avantages DPE)
- [x] **lp-multi-travaux/index.html** - Landing multi-projets (violet, choix solaire/PAC/isolation)

**URLs LIVE (vérifiées sur Vercel) :**
- https://solar-forms-hub.vercel.app/landing-pages/lp-panneaux-solaires/
- https://solar-forms-hub.vercel.app/landing-pages/lp-pompe-a-chaleur/
- https://solar-forms-hub.vercel.app/landing-pages/lp-isolation-exterieure/
- https://solar-forms-hub.vercel.app/landing-pages/lp-multi-travaux/

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

## PROCHAINES TÂCHES (À FAIRE)

### CIBLE : Propriétaires de maison en France
### OBJECTIF : MAXIMUM DE LEADS / CONVERSION (exagération autorisée !)

---

### 1. LANDING PAGES RESTANTES (dossier `/landing-pages/`)

- [ ] **lp-simulateur-aides/index.html** - Simulateur MaPrimeRénov / CEE / aides ← PROCHAIN
- [ ] **`/landing-pages/index.html`** - Hub de présentation de toutes les landing pages

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
├── landing-pages/                ← 4 PAGES CRÉÉES ✅
│   ├── lp-panneaux-solaires/     ✅ FAIT - Orange, solaire PV
│   ├── lp-pompe-a-chaleur/       ✅ FAIT - Bleu, PAC air/eau
│   ├── lp-isolation-exterieure/  ✅ FAIT - Vert, ITE
│   ├── lp-multi-travaux/         ✅ FAIT - Violet, 3 projets
│   └── lp-simulateur-aides/      ← À FAIRE
│
└── versions-completes/           ← V1 à V14 (FAIT)
    ├── v1-neon/
    ├── v2-nature/
    ... (V1 à V14)
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
✅ Animations AOS + Confetti
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

# DÉPLOYER sur Vercel :
npx vercel --prod --yes

# ⚠️ NE PAS UTILISER web_fetch_vercel_url pour vérifier !
# Ça télécharge tout le HTML et consomme trop de tokens.
# Faire confiance au déploiement si "Production" s'affiche.

# URL projet : https://solar-forms-hub.vercel.app/

# SI FIN DE CONTEXTE → mettre à jour ce TODO + écrire prompt pour le suivant
```

---

## PROMPT POUR LE PROCHAIN AGENT

```
Lis le fichier TODO-NEXT.md dans le projet solar-forms-hub et continue les tâches.

CONTEXTE :
- 4 landing pages sont TERMINÉES et LIVE (solaire, PAC, isolation, multi-travaux)
- URLs : voir section "FAIT (Agent 3)" dans le TODO
- Prochaine tâche : créer lp-simulateur-aides/index.html

IMPORTANT :
- Utilise les données Perplexity déjà récupérées dans ce fichier
- EXAGÈRE les chiffres et l'urgence pour maximiser les leads
- Utilise AOS + Confetti pour les animations
- Cible = propriétaires de maison en France
- Après chaque création : git add, commit, push, PUIS npx vercel --prod --yes
- Mets à jour ce TODO au fur et à mesure
- Ne dis JAMAIS "c'est terminé" sans avoir vérifié sur Vercel
- SI FIN DE CONTEXTE → mets à jour ce TODO + écris prompt suivant
```

---

*Mis à jour le 1er décembre 2025 - Agent 3*
