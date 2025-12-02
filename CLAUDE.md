# Instructions Claude - Solar Forms Hub

## Projet
Site de generation de leads renovation energetique (solaire, PAC, isolation).
Cible : proprietaires de maison en France.
URL : https://solar-forms-hub.vercel.app/

## Structure du projet (MAJ 02/12/2025)

```
solar-forms-hub/
├── index.html                    # Dashboard principal
├── multi-sites/
│   └── eligibilite-clone/        # SITE STAR - 9 pages V4
└── .playwright-mcp/              # Screenshots Playwright
```

## Eligibilite Clone V4 - Site Complet (9 pages)

**URL** : https://solar-forms-hub.vercel.app/multi-sites/eligibilite-clone/

### Architecture
```
eligibilite-clone/
├── index.html              # Landing principale
├── formulaire.html         # Formulaire 5 etapes
├── merci.html              # Page confirmation
├── panneaux-solaires.html  # Page dispositif solaire
├── isolation.html          # Page dispositif isolation
├── pompe-a-chaleur.html    # Page dispositif PAC
├── maprimerenov.html       # Page aide MPR
├── prime-cee.html          # Page aide CEE
├── anah.html               # Page aide Anah
├── images/                 # 21 images (hero, cards, icones)
├── DONNEES-2025.md         # Baremes officiels 2025
└── PROMPT-V5-ENRICHISSEMENT.md  # Prochaine etape
```

### Navigation Dropdown (implementee)
- Menu "Les dispositifs" : Solaire, Isolation, PAC
- Menu "Les aides" : MaPrimeRenov, Prime CEE, Anah
- FAQ + CTA "Je teste mon eligibilite"

### Images existantes (21)
```
images/
├── hero-*.jpg (6)     # Heroes pages
├── card-*.jpg (3)     # Cards dispositifs
├── icon-*.jpg (3)     # Icones aides
├── famille-*.jpg (4)  # Familles/couples
├── step*.jpg (3)      # Etapes processus
└── autres (2)         # Artisan, maison
```

## Prochaine etape : V5 - Enrichissement Visuel

Lire `PROMPT-V5-ENRICHISSEMENT.md` pour :
- Generer 15+ nouvelles images IA (humains, demonstrations)
- Integrer sur les 9 pages
- Objectif : conversion maximale

## Regles techniques
- HTML/CSS/JS vanilla (pas de framework)
- Un fichier HTML par page
- CDN : AOS, FontAwesome, Google Fonts
- Mobile-first (375px+)
- < 100KB par page

## Generation images IA (Fal.ai)

```javascript
mcp__fal-ai__run_model({
    model_id: "fal-ai/flux/dev",
    input: {
        prompt: "...",
        num_images: 1,
        image_size: "landscape_16_9"
    }
})
// Puis : curl -o "images/nom.jpg" "URL"
```

## Deploiement
```bash
git add . && git commit -m "description"
git push
npx vercel --prod --yes
```

## MCP utiles
- fal-ai : generation images
- playwright : tests visuels
- vercel : deploiement
- perplexity : recherche web
- github : commits

## Screenshots V4 (.playwright-mcp/)
- v4-index-desktop.png
- v4-solaire-desktop.png
- v4-mpr-desktop.png
