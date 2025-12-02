# Instructions Claude - Solar Forms Hub

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
