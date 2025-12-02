# Instructions Claude - Solar Forms Hub

## Projet
Site de generation de leads renovation energetique (solaire, PAC, isolation).
Cible : proprietaires de maison en France.
URL : https://solar-forms-hub.vercel.app/

## Structure du projet (MAJ 02/12/2025)

```
solar-forms-hub/
├── index.html                    # Dashboard principal
├── renovation-energie-2025.html  # LP Premium multi-activites
├── landing-pages/
│   ├── lp-prime-renovation/     # NEW - Style primerenovation-en-ligne.com
│   ├── lp-panneaux-solaires/    # LP Solaire V1 (orange)
│   ├── lp-panneaux-solaires-v2/ # LP Solaire V2 premium (images IA)
│   ├── lp-pompe-a-chaleur/      # LP PAC (bleu)
│   ├── lp-isolation-exterieure/ # LP Isolation (vert)
│   ├── lp-multi-travaux/        # LP Multi-projets (violet)
│   └── lp-simulateur-aides/     # LP Simulateur (rose)
├── versions-completes/          # 14 versions formulaires (V1-V14)
├── public/images/               # Images IA generees
│   └── prime-reno/              # 12 images pour LP Prime Renovation
└── TODO.md                      # Fichier TODO a jour
```

## Pages actives (8 total)

| Page | URL | Description |
|------|-----|-------------|
| Dashboard | / | Page d'accueil avec toutes les LP |
| Prime Renovation | /landing-pages/lp-prime-renovation/ | NEW - Style pro bleu |
| Renovation 2025 | /renovation-energie-2025.html | Multi-activites + simulateur |
| Solaire V2 | /landing-pages/lp-panneaux-solaires-v2/ | Premium avec images IA |
| Solaire V1 | /landing-pages/lp-panneaux-solaires/ | Theme orange |
| PAC | /landing-pages/lp-pompe-a-chaleur/ | Theme bleu, 11000€ aides |
| Isolation | /landing-pages/lp-isolation-exterieure/ | Theme vert, 75€/m2 |
| Multi-Travaux | /landing-pages/lp-multi-travaux/ | Theme violet |
| Simulateur | /landing-pages/lp-simulateur-aides/ | Theme rose |

## Regles techniques
- HTML/CSS/JS vanilla uniquement (pas de framework)
- Tout dans un seul fichier HTML par page
- CDN uniquement (AOS, FontAwesome, Google Fonts)
- Mobile-first obligatoire
- < 200KB par fichier HTML
- Images dans public/images/

## Generation d'images IA (Fal.ai)

IMPORTANT: Utiliser `mcp__fal-ai__run_model` (PAS generate_image qui bug)
```
model_id: "fal-ai/flux/dev"
input: {"prompt": "...", "num_images": 1, "image_size": "landscape_16_9"}
```
Puis telecharger: `curl -o "public/images/nom.jpg" "URL_RETOURNEE"`

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
