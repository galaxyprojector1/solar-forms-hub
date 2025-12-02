# Instructions Claude - Solar Forms Hub

## MISSION PRINCIPALE (Prochaine session)

### Objectif
Refaire TOUTES les pages du site en version ULTRA PREMIUM avec :
- 20-30 images IA generees avec Fal.ai (modele: fal-ai/flux/dev)
- Design moderne, animations fluides, conversion maximale
- Mobile-first, dark mode elegant

### TODO Liste
1. [ ] Generer 20+ images IA (hero, services, temoignages, backgrounds)
2. [ ] Refaire renovation-energie-2025.html (page principale)
3. [ ] Refaire LP Panneaux Solaires V2 premium
4. [ ] Refaire LP Pompe a Chaleur premium
5. [ ] Refaire LP Isolation premium
6. [ ] Refaire LP Multi-Travaux premium
7. [ ] Refaire LP Simulateur premium
8. [ ] Mettre a jour dashboard index.html
9. [ ] Deployer sur Vercel

### Images a generer avec Fal.ai

**IMPORTANT**: Utiliser `mcp__fal-ai__run_model` (pas generate_image)
```
model_id: "fal-ai/flux/dev"
input: {"prompt": "...", "num_images": 1, "image_size": "landscape_16_9"}
```
Puis telecharger: `curl -o "public/images/nom.jpg" "URL"`

**Liste des images a generer:**

HERO IMAGES (1920x1080):
1. hero-main.jpg - "Modern French house with solar panels on roof, heat pump unit, green garden, sunny day, photorealistic, architectural photography, 4k"
2. hero-solar.jpg - "Close-up of premium black solar panels on terracotta roof tiles, French countryside background, golden hour light, professional photography"
3. hero-pac.jpg - "Modern white heat pump unit installed outside beautiful French stone house, clean design, professional installation, daylight"
4. hero-isolation.jpg - "Workers installing exterior wall insulation on French house, professional team, safety equipment, bright day"
5. hero-ev.jpg - "Electric car charging at home wallbox charger, modern French house garage, Tesla-style, evening ambient lighting"

SERVICES CARDS (800x600):
6. service-solar.jpg - "Aerial view of house with solar panel installation, French suburban neighborhood, drone photography style"
7. service-pac.jpg - "Split image showing heat pump exterior unit and cozy warm interior living room, modern home"
8. service-isolation.jpg - "Cross-section view showing wall insulation layers, technical illustration style but photorealistic"
9. service-ev.jpg - "Sleek EV charging station with illuminated logo, night shot, premium quality"

TESTIMONIALS (400x400):
10. client-1.jpg - "Professional headshot of French woman 40s, friendly smile, natural lighting, neutral background"
11. client-2.jpg - "Professional headshot of French man 50s, confident, business casual, warm lighting"
12. client-3.jpg - "Professional headshot of young French couple 30s, happy, outdoor background blur"

BACKGROUNDS (1920x1080):
13. bg-gradient.jpg - "Abstract gradient background dark blue to emerald green, subtle geometric patterns, modern"
14. bg-tech.jpg - "Futuristic energy grid visualization, green and blue glowing lines, dark background"
15. bg-nature.jpg - "Aerial view of French countryside with wind turbines and solar farms, sustainable energy"

ICONS/DETAILS (600x600):
16. detail-savings.jpg - "Stack of euro bills with green energy symbols, savings concept, clean white background"
17. detail-certificate.jpg - "RGE certification badge with French flag colors, official looking, 3D render"
18. detail-guarantee.jpg - "25 year warranty badge, gold and green, premium quality seal"
19. detail-eco.jpg - "Green leaf transforming into house shape, eco-friendly concept, minimalist"
20. detail-france.jpg - "Map of France with glowing energy network, data visualization style"

### Design Guidelines

**Palette de couleurs:**
- Primary: #10B981 (emerald green)
- Secondary: #3B82F6 (blue)
- Accent: #F59E0B (orange/solar)
- Dark: #0F172A, #1E293B
- Light: #F8FAFC, #E2E8F0

**Typographie:**
- Font: Inter (Google Fonts)
- Titres: 700, grandes tailles
- Corps: 400/500, lisible

**Animations:**
- AOS (Animate On Scroll) pour les sections
- Hover effects sur les cartes
- Smooth scroll
- Confetti sur conversion

**Structure de chaque LP:**
1. Hero section (image plein ecran + titre + CTA)
2. Stats bar (chiffres cles animes)
3. Avantages (3-4 cartes avec icones)
4. Comment ca marche (timeline)
5. Aides disponibles (tableau comparatif)
6. Temoignages (carousel)
7. FAQ (accordion)
8. CTA final (formulaire ou bouton)
9. Footer

### Criteres de qualite
- Lighthouse score > 90
- Mobile responsive parfait
- Temps de chargement < 3s
- Images optimisees (webp si possible)
- SEO meta tags complets
- Schema.org markup

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
