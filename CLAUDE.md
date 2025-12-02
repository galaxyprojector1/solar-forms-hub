# Instructions Claude - Solar Forms Hub

## MISSION PRINCIPALE - CREER UN SITE 10X MIEUX

### Contexte
Tu dois CREER une NOUVELLE landing page ULTRA PREMIUM pour la renovation energetique.
Le site actuel est visible sur : https://solar-forms-hub.vercel.app/
Tu dois faire 10X MIEUX que ce qui existe.

### ETAPE 1 : RECHERCHE (OBLIGATOIRE)

**Avant de coder, tu DOIS :**

1. **Analyser le site actuel avec Playwright**
   - Aller sur https://solar-forms-hub.vercel.app/
   - Visiter TOUTES les pages existantes (renovation-energie-2025.html, landing-pages/*)
   - Prendre des screenshots pour comprendre le design actuel
   - Noter ce qui marche et ce qui peut etre ameliore

2. **Chercher l'inspiration avec Perplexity/WebSearch**
   - Rechercher "best solar panel landing page design 2025"
   - Rechercher "meilleurs sites renovation energetique France"
   - Rechercher "high converting energy landing page examples"
   - Rechercher "MaPrimeRenov 2025 montants aides officiels"
   - S'inspirer des meilleurs sites du secteur

3. **Verifier les donnees officielles**
   - Montants MaPrimeRenov 2025 a jour
   - Plafonds CEE actuels
   - Montants Eco-PTZ
   - TVA reduite conditions

### ETAPE 2 : GENERATION D'IMAGES IA

**Utiliser Fal.ai pour generer 20-30 images premium**

IMPORTANT: Utiliser `mcp__fal-ai__run_model` (PAS generate_image qui bug)
```
model_id: "fal-ai/flux/dev"
input: {"prompt": "...", "num_images": 1, "image_size": "landscape_16_9"}
```
Puis telecharger: `curl -o "public/images/nom.jpg" "URL_RETOURNEE"`

**Images a generer (adapte selon ton inspiration) :**
- Hero images spectaculaires (maisons avec panneaux solaires, PAC, etc)
- Photos de services (installations, equipements)
- Portraits clients pour temoignages
- Backgrounds abstraits/tech
- Icones et badges (garantie, certifications)

Ne pas hesiter sur le nombre d'images - budget illimite !

### ETAPE 3 : CREER LA NOUVELLE PAGE

**Creer : `landing-pages/lp-premium-2025/index.html`**

La page doit etre :
- SPECTACULAIRE visuellement
- Mobile-first parfait
- Animations fluides (AOS)
- Conversion maximale
- Chargement rapide

**Structure recommandee :**
1. Hero plein ecran avec video/image + titre impactant + CTA
2. Barre de stats animees (90% aides, 50000€ eco-ptz, etc)
3. Section services avec belles images IA
4. Section aides financieres detaillees
5. Simulateur interactif
6. Temoignages clients avec photos
7. FAQ accordion
8. CTA final puissant
9. Footer complet

### ETAPE 4 : METTRE A JOUR LE DASHBOARD

**Modifier index.html pour afficher la nouvelle page**
- Ajouter la nouvelle LP en position premium
- Mettre a jour les compteurs
- S'assurer que tous les liens fonctionnent

### ETAPE 5 : DEPLOYER

```bash
git add .
git commit -m "Nouvelle LP Premium 2025 avec images IA"
git push
npx vercel --prod --yes
```

Puis verifier avec Playwright que tout fonctionne.

### TODO Liste
1. [ ] Recherche : analyser site actuel avec Playwright
2. [ ] Recherche : chercher inspiration meilleurs sites energie
3. [ ] Recherche : verifier donnees aides 2025 officielles
4. [ ] Generer 20-30 images IA avec Fal.ai
5. [ ] Creer landing-pages/lp-premium-2025/index.html
6. [ ] Mettre a jour dashboard index.html
7. [ ] Deployer sur Vercel
8. [ ] Verifier le resultat final avec Playwright

### Regles techniques
- HTML/CSS/JS vanilla uniquement
- Tout dans un seul fichier HTML
- CDN uniquement (pas de fichiers locaux sauf images)
- Mobile-first obligatoire
- < 200KB par fichier HTML
- Images dans public/images/

### Style marketing
- Exagerer les economies et aides pour maximiser les leads
- Urgence : "Offre limitee", "Aides en baisse en 2026"
- Social proof : temoignages, nombre de clients
- Confiance : certifications RGE, garanties

---

## Projet
Site de generation de leads renovation energetique (solaire, PAC, isolation).
Cible : proprietaires de maison en France.

## Structure du projet (MAJ 02/12/2025)

```
solar-forms-hub/
├── index.html                    # Dashboard principal (dark mode)
├── renovation-energie-2025.html  # Site premium multi-activites
├── landing-pages/
│   ├── index.html               # Index des LP
│   ├── lp-panneaux-solaires/    # LP Solaire V1 (orange)
│   ├── lp-panneaux-solaires-v2/ # LP Solaire V2 premium (images IA)
│   ├── lp-pompe-a-chaleur/      # LP PAC (bleu)
│   ├── lp-isolation-exterieure/ # LP Isolation (vert)
│   ├── lp-multi-travaux/        # LP Multi-projets (violet)
│   └── lp-simulateur-aides/     # LP Simulateur (rose)
├── versions-completes/          # 14 versions formulaires (V1-V14)
│   ├── v1-neon/
│   ├── v2-nature/
│   ├── v3-glass/
│   ├── v4-minimal/
│   ├── v5-particles/
│   ├── v6-morphing/
│   ├── v7-3d/
│   ├── v8-gamification/
│   ├── v9-story/
│   ├── v10-simulation/
│   ├── v11-clean/
│   ├── v12-trust/
│   ├── v13-urgency/
│   └── v14-mobile/
├── public/images/               # Images IA generees
└── formulaires/                 # Dossiers vides (a faire)
```

## Pages actives (7 total)

| Page | URL | Description |
|------|-----|-------------|
| Dashboard | / | Page d'accueil dark mode |
| Site Premium | /renovation-energie-2025.html | Multi-activites + simulateur |
| LP Solaire V2 | /landing-pages/lp-panneaux-solaires-v2/ | Premium avec images IA |
| LP Solaire V1 | /landing-pages/lp-panneaux-solaires/ | Theme orange |
| LP PAC | /landing-pages/lp-pompe-a-chaleur/ | Theme bleu, 11000 aides |
| LP Isolation | /landing-pages/lp-isolation-exterieure/ | Theme vert, 75/m2 |
| LP Multi | /landing-pages/lp-multi-travaux/ | Theme violet |
| LP Simulateur | /landing-pages/lp-simulateur-aides/ | Theme rose |

## Regles de code
- HTML/CSS/JS vanilla uniquement (pas de framework)
- Tout dans un seul fichier HTML par page
- CDN uniquement, pas de fichiers locaux
- Mobile-first obligatoire
- < 200KB par fichier

## MCP a activer
```
/mcp -> activer : vercel, github, playwright, perplexity, context7
/mcp -> desactiver : fal-ai, supabase, n8n-api, n8n-workflows-docs
```

## Apres chaque modification
```bash
git add . && git commit -m "description"
git push
npx vercel --prod --yes
```

## Style marketing
- Exagerer les economies et aides pour maximiser les leads
- Toujours inclure : urgence, social proof, temoignages
- Animations : AOS, confetti

## URLs
- Prod : https://solar-forms-hub.vercel.app/
- Landing pages : https://solar-forms-hub.vercel.app/landing-pages/
