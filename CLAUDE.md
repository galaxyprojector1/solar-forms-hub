# Instructions Claude - Solar Forms Hub

## Projet
Site de generation de leads renovation energetique (solaire, PAC, isolation).
Cible : proprietaires de maison en France.
URL : https://solar-forms-hub.vercel.app/

## Structure du projet (MAJ 02/12/2025)

```
solar-forms-hub/
├── index.html                    # Dashboard principal (TOUJOURS METTRE A JOUR)
├── renovation-energie-2025.html  # LP Premium multi-activites
├── landing-pages/
│   ├── lp-prime-renovation/     # Style primerenovation-en-ligne.com
│   ├── lp-panneaux-solaires/    # LP Solaire V1 (orange)
│   ├── lp-panneaux-solaires-v2/ # LP Solaire V2 premium (images IA)
│   ├── lp-pompe-a-chaleur/      # LP PAC (bleu)
│   ├── lp-isolation-exterieure/ # LP Isolation (vert)
│   ├── lp-multi-travaux/        # LP Multi-projets (violet)
│   └── lp-simulateur-aides/     # LP Simulateur (rose)
├── multi-sites/                  # Clones de sites concurrents
│   ├── eligibilite-clone/       # V2 - Formulaire multi-etapes + animations
│   └── prime-energie-pro/       # Clone eligibilite.com ameliore
├── versions-completes/          # 14 versions formulaires (V1-V14)
├── public/images/               # Images IA generees
└── .playwright-mcp/             # Screenshots Playwright
```

## REGLE IMPORTANTE - Dashboard

**TOUJOURS mettre a jour index.html (dashboard) quand on ajoute une nouvelle page !**
- Ajouter la carte dans la section appropriee (Landing Pages ou Multi-Sites)
- Mettre a jour les compteurs dans le header
- Commit + push + deploy pour que ce soit visible sur https://solar-forms-hub.vercel.app/

## Pages actives

| Page | URL | Description |
|------|-----|-------------|
| Dashboard | / | Page d'accueil avec toutes les LP |
| **Eligibilite Clone V2** | /multi-sites/eligibilite-clone/ | **STAR** - Formulaire 5 etapes + animations |
| Prime Energie Pro | /multi-sites/prime-energie-pro/ | Clone ameliore |
| Prime Renovation | /landing-pages/lp-prime-renovation/ | Style pro bleu |
| Renovation 2025 | /renovation-energie-2025.html | Multi-activites + simulateur |
| Solaire V2 | /landing-pages/lp-panneaux-solaires-v2/ | Premium avec images IA |
| Solaire V1 | /landing-pages/lp-panneaux-solaires/ | Theme orange |
| PAC | /landing-pages/lp-pompe-a-chaleur/ | Theme bleu, 11000€ aides |
| Isolation | /landing-pages/lp-isolation-exterieure/ | Theme vert, 75€/m2 |
| Multi-Travaux | /landing-pages/lp-multi-travaux/ | Theme violet |
| Simulateur | /landing-pages/lp-simulateur-aides/ | Theme rose |

## Eligibilite Clone V2 - Features

La page star du projet avec toutes les features avancees :

### Animations
- Hero : texte mot par mot (typewriter effect)
- Gradient anime en background
- Trust badge floating
- Compteur anime des avis (0 → 126)
- Pulse/glow sur boutons CTA
- Confetti a la soumission
- Cards 3D hover effects

### Formulaire Multi-Etapes (5 steps)
1. **Projet** : PAC, isolation, solaire, chaudiere, VMC, fenetres, multi
2. **Logement** : type, proprietaire/locataire, annee construction, surface
3. **Chauffage** : type actuel, facture annuelle energie
4. **Revenus** : nombre personnes foyer, revenu fiscal reference
5. **Contact** : nom, prenom, email, telephone, code postal, consentement

### UX/UI
- Progress bar animee avec etapes
- Estimation dynamique des aides (calcul en temps reel)
- Validation temps reel des champs
- Recapitulatif avant envoi
- Animation succes spectaculaire

### Mobile (375px+)
- Menu hamburger fullscreen
- Sticky CTA en bas
- Touch swipe entre etapes
- Options 2 colonnes puis 1 colonne
- Boutons 48px minimum (touch-friendly)

### Performance
- Header dark mode au scroll (backdrop-filter blur)
- Lazy loading images natif
- GPU accelerated animations
- Preload Google Fonts

## Regles techniques
- HTML/CSS/JS vanilla uniquement (pas de framework)
- Tout dans un seul fichier HTML par page
- CDN uniquement (AOS, FontAwesome, Google Fonts)
- Mobile-first obligatoire
- < 200KB par fichier HTML
- Images dans le dossier images/ de chaque page ou public/images/

## Generation d'images IA (Fal.ai)

IMPORTANT: Utiliser `mcp__fal-ai__run_model` (PAS generate_image qui bug)
```
model_id: "fal-ai/flux/dev"
input: {"prompt": "...", "num_images": 1, "image_size": "landscape_16_9"}
```
Puis telecharger: `curl -o "chemin/images/nom.jpg" "URL_RETOURNEE"`

## Deploiement
```bash
git add . && git commit -m "description"
git push
npx vercel --prod --yes
```

## Style marketing
- Exagerer les economies et aides pour maximiser les leads
- Urgence : "Offre limitee", "Aides en baisse en 2026"
- Social proof : temoignages, nombre de clients
- Confiance : certifications RGE, garanties
- Animations : AOS pour les scroll effects

## MCP utiles
- vercel : deploiement
- github : commits
- playwright : tests visuels
- perplexity : recherche web
- fal-ai : generation images
- context7 : documentation libs

## Screenshots disponibles (.playwright-mcp/)
- eligibilite-v2-desktop-hero.png
- eligibilite-v2-formulaire-desktop.png
- eligibilite-v2-mobile-hero.png
- eligibilite-v2-mobile-formulaire.png
