# BMAD Project Context - Éligibilité V4

---
## ⚠️ IMPORTANT - INSTALLER BMAD D'ABORD

Si pas encore fait, exécute dans le terminal :
```bash
npx bmad-method@alpha install
```

Puis utilise les commandes BMAD : `*workflow-init`, `*prd`, `*create-architecture`

---

## PROJECT OVERVIEW

### Current State
- **V3 Form COMPLETE**: `formulaire.html` is done with multi-select aids, slow transitions (700ms), encouragement messages, animated region loader
- **Pages need redesign**: All other HTML pages need premium redesign focused on conversion

### Business Goal
Maximize conversions (form submissions) by putting **FINANCIAL AIDS** front and center.

### Target Persona
- Age: 45-65 years old
- Status: Homeowner (individual house)
- Motivation: Reduce energy bills, improve comfort
- Barriers: Administrative complexity, fear of scams
- Behavior: Mobile-first, limited attention, needs reassurance

---

## PAGES TO REDESIGN (Priority Order)

| Page | Status | Priority |
|------|--------|----------|
| `index.html` | To redesign | 1 - HIGHEST |
| `maprimerenov.html` | To redesign | 2 |
| `prime-cee.html` | To redesign | 3 |
| `pompe-a-chaleur.html` | To redesign | 4 |
| `isolation.html` | To redesign | 5 |
| `panneaux-solaires.html` | To redesign | 6 |
| `anah.html` | To redesign | 7 |
| `formulaire.html` | DONE (V3) | - |
| `merci.html` | OK as is | - |

---

## AVAILABLE ASSETS

### Images (30 files in images/)

**Heroes/Backgrounds:**
- hero-couple.jpg, famille-reference.jpg, famille-jardin.jpg
- modern-eco-house.jpg, french-house-garden.jpg, cozy-winter-interior.jpg

**Work Types:**
- hero-pac.jpg, hero-isolation.jpg, hero-solaire.jpg
- card-pac.jpg, card-isolation.jpg, card-solaire.jpg
- heatpump-diagram.jpg, thermography-house.jpg
- roof-solar-comparison.jpg, facade-before-after.jpg

**Professionals:**
- artisan-heatpump.jpg, rge-certified-artisan.jpg
- technician-roof-solar.jpg, energy-advisor.jpg

**Aid Icons:**
- icon-mpr.jpg, icon-cee.jpg, icon-anah.jpg

**Steps:**
- step1-selection.jpg, step2-eligibility.jpg, step3-artisan.jpg

**Other:**
- energy-bill-savings.jpg, maprimerenov-document.jpg
- senior-couple-solar.jpg, family-warm-living.jpg

---

## 2025 AID DATA

### MaPrimeRénov' by Profile

**BLUE Profile (Very Modest):**
- Heat pump air-water: 5,000€
- Geothermal heat pump: 11,000€
- Wall insulation: 75€/m²
- Attic insulation: 25€/m²
- Solar water heater: 4,000€

**YELLOW Profile (Modest):**
- Heat pump air-water: 4,000€
- Geothermal heat pump: 9,000€
- Wall insulation: 60€/m²
- Attic insulation: 20€/m²
- Solar water heater: 3,000€

**PURPLE Profile (Intermediate):**
- Heat pump air-water: 3,000€
- Geothermal heat pump: 6,000€
- Wall insulation: 40€/m²
- Attic insulation: 15€/m²
- Solar water heater: 2,000€

### CEE Premiums by Climate Zone

| Work | Zone H1 | Zone H2 | Zone H3 |
|------|---------|---------|---------|
| Heat pump | 4,500€ | 3,800€ | 2,500€ |
| Attic insulation | 12€/m² | 10€/m² | 8€/m² |
| Wall insulation | 15€/m² | 12€/m² | 10€/m² |

### Regional Aids
- Île-de-France: 2,000€
- Auvergne-Rhône-Alpes: 1,500€
- Occitanie: 1,500€
- Grand Est: 1,000€
- Hauts-de-France: 1,500€
- Nouvelle-Aquitaine: 1,200€

### Maximum Combined Aid
- Blue: 100% of cost
- Yellow: 90% of cost
- Purple: 75% of cost
- Pink: 60% of cost

---

## DESIGN REQUIREMENTS

### Colors
```css
--blue-dark: #1E3A8A      /* Trust */
--blue-primary: #2563EB   /* Links */
--orange: #F97316         /* CTAs */
--green: #10B981          /* Money/Success */
--bleu-mpr: #3B82F6
--jaune-mpr: #F59E0B
--violet-mpr: #8B5CF6
```

### Typography
- Font: Inter (Google Fonts)
- Hero titles: 2rem mobile / 3.5rem desktop, weight 900
- Amounts: 2.5rem mobile / 4rem desktop, weight 900, green color
- Body: 1rem, line-height 1.6

### Components
- CTAs: 60px min-height, border-radius 16px, orange gradient, pronounced shadows
- Cards: White bg, border-radius 24px, hover lift effect (-8px translateY)
- Trust badges: Pill shape, white/transparent bg, green checkmark icon
- Sticky CTA: Fixed bottom on mobile, blue gradient

### Accessibility (Seniors 40-50+)
- Touch targets: 48px minimum
- Slow transitions: 700ms
- Large readable text
- High contrast
- prefers-reduced-motion support

---

## TECHNICAL CONSTRAINTS

- HTML/CSS/JS vanilla (single file per page)
- Mobile-first 375px
- < 100KB per page (excluding images)
- Images lazy loading
- Icons: Font Awesome 6
- Fonts: Inter via Google Fonts

---

## KEY CONVERSION ELEMENTS

### Headlines
- "Jusqu'à 25 000€ d'aides pour vos travaux"
- "90% des propriétaires sont éligibles"
- "Simulation gratuite en 2 minutes"

### Trust Badges
- "100% gratuit et sans engagement"
- "Données officielles 2025"
- "Artisans RGE certifiés"
- "15 000+ simulations réalisées"

### CTAs Text
- "Tester mon éligibilité →"
- "Calculer mes aides →"
- "Commencer ma simulation →"

### Testimonials
- "J'ai reçu 8 500€ d'aides pour ma pompe à chaleur." - Jean-Pierre, 62 ans
- "12 000€ pour isoler ma maison !" - Marie, 58 ans
- "Simple et rapide, rappelé le lendemain." - Patrick, 55 ans

---

## WORKFLOW ORCHESTRATION

### Parallel Agents Strategy
Launch multiple agents simultaneously for efficiency:

```
PARALLEL TASKS EXAMPLE:
├── Agent 1: Research (Perplexity) - Latest 2025 aid amounts, regulations
├── Agent 2: Copywriting - Generate headlines, CTAs, testimonials
├── Agent 3: Design - Create page structure, components
└── Agent 4: Assets - Generate missing images with Fal.ai
```

### Iteration & Self-Verification Loop
After EACH page redesign, run this checklist:

```
VERIFICATION LOOP:
1. Playwright screenshot mobile 375px
2. Check: All CTAs visible above fold?
3. Check: Aid amounts in BIG GREEN numbers?
4. Check: Sticky CTA present on mobile?
5. Check: No console errors?
6. If FAIL → Fix and re-verify
7. If PASS → Move to next page
```

### Research Tasks (Perplexity)
Before starting, research:
- "MaPrimeRénov barèmes 2025 officiel"
- "Prime CEE montants 2025"
- "Aides rénovation énergétique décembre 2025"
- "Meilleurs landing pages conversion rénovation"

---

## MCP TOOLS - DETAILED USAGE

### 1. Perplexity (Research)
```
mcp__perplexity__perplexity_search - Quick facts
mcp__perplexity__perplexity_research - Deep research with citations
mcp__perplexity__perplexity_ask - Conversational queries
```
**USE FOR**: Latest 2025 aid amounts, regulations, competitor analysis

### 2. Fal.ai (Image Generation)
**IMPORTANT**: Use `mcp__fal-ai__run_model` (NOT generate_image)
```
BEST MODELS:
- Quality: "fal-ai/recraft-v3" (illustrations, icons)
- Photos: "fal-ai/flux/dev" ($0.025/MP)
- Fast: "fal-ai/flux/schnell" ($0.003/img)

EXAMPLE:
model_id: "fal-ai/flux/dev"
input: {
  "prompt": "French senior couple smiling in front of modern house with heat pump, sunny day, professional photo",
  "num_images": 1,
  "image_size": "landscape_16_9"
}
```
Then download: `curl -o "image.jpg" "URL_RETURNED"`

### 3. Playwright (Testing & QA)
```
mcp__playwright__browser_navigate - Load page
mcp__playwright__browser_resize - Set to 375x812 (mobile)
mcp__playwright__browser_snapshot - Get page structure
mcp__playwright__browser_take_screenshot - Visual proof
mcp__playwright__browser_click - Test CTAs
```
**USE FOR**: Every page after redesign, verify mobile 375px

### 4. Vercel (Deploy)
```
mcp__vercel__deploy_to_vercel - Deploy current project
mcp__vercel__list_deployments - Check deployment status
```
Team ID: `team_hUdxj5fLD8qLSwpYk0CfNvb9`

### 5. Context7 (Documentation)
```
mcp__context7__resolve-library-id - Find library
mcp__context7__get-library-docs - Get docs
```
**USE FOR**: AOS animations, CSS techniques, accessibility

### 6. GitHub (Research)
```
mcp__github__search_code - Find code examples
mcp__github__get_file_contents - Read files from repos
```
**USE FOR**: Landing page examples, conversion patterns

---

## COPYWRITING GUIDELINES

### Tone & Style
- **Direct**: No fluff, straight to the point
- **Urgent**: "Aides en baisse en 2026", "Profitez maintenant"
- **Reassuring**: "100% gratuit", "Sans engagement", "Officiel"
- **Personal**: "Vos aides", "Votre maison", "Calculez VOS économies"

### Power Words (French)
```
URGENCY: Maintenant, Aujourd'hui, Dernière chance, Avant la baisse
MONEY: Gratuit, Économisez, Jusqu'à X€, Financé à 90%
TRUST: Officiel, Certifié, Garanti, Vérifié, RGE
ACTION: Découvrez, Calculez, Testez, Obtenez, Profitez
```

### Headline Formulas
```
1. [MONTANT] d'aides pour [TRAVAUX] - "Jusqu'à 11 000€ pour votre pompe à chaleur"
2. [POURCENTAGE] des [CIBLE] sont éligibles - "90% des propriétaires sont éligibles"
3. [ACTION] en [TEMPS] - "Calculez vos aides en 2 minutes"
4. [BÉNÉFICE] + [PREUVE] - "Divisez vos factures par 3 comme 15 000 foyers"
```

### CTA Formulas
```
PRIMARY (Orange): "Calculer mes aides →" / "Tester mon éligibilité →"
SECONDARY (Blue): "En savoir plus" / "Voir les conditions"
URGENCY (Red accent): "Derniers jours pour en profiter →"
```

---

## SUCCESS CRITERIA

- [ ] All CTAs visible and clickable on mobile 375px
- [ ] Aid amounts displayed prominently (big green numbers)
- [ ] Sticky CTA on mobile
- [ ] Testimonials with real amounts
- [ ] Trust badges visible above fold
- [ ] Page loads < 2.5s LCP
- [ ] Lighthouse score > 90
- [ ] All images loaded
- [ ] No console errors
