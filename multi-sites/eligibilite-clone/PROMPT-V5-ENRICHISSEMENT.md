# PROMPT V5 - Eligibilite Clone - Enrichissement Visuel + Maillage

## OBJECTIF

Enrichir les 9 pages existantes avec :
- **Images IA creatives** (humains, demonstrations, avant/apres)
- **Maillage interne** entre toutes les pages (liens croises)
- **Parcours utilisateur** optimise vers le formulaire

**BUT FINAL** : Maximiser les soumissions de formulaire (conversion)

**URL** : https://solar-forms-hub.vercel.app/multi-sites/eligibilite-clone/

---

## ARCHITECTURE ACTUELLE (9 pages)

```
multi-sites/eligibilite-clone/
├── index.html              # Landing principale
├── formulaire.html         # Formulaire 5 etapes
├── merci.html              # Page confirmation
├── panneaux-solaires.html  # Dispositif solaire
├── isolation.html          # Dispositif isolation
├── pompe-a-chaleur.html    # Dispositif PAC
├── maprimerenov.html       # Aide MPR
├── prime-cee.html          # Aide CEE
├── anah.html               # Aide Anah
├── images/                 # 21 images existantes
└── DONNEES-2025.md         # Baremes et donnees officielles
```

---

## IMAGES EXISTANTES

```
images/
├── hero-couple.jpg           # Couple devant maison
├── hero-famille-moderne.jpg  # Famille moderne
├── famille-reference.jpg     # Famille reference
├── famille-jardin.jpg        # Famille jardin
├── famille-economie.jpg      # Famille economies
├── success-thumbsup.jpg      # Succes pouce leve
├── conseiller-telephone.jpg  # Conseiller au tel
├── artisan-installation.jpg  # Artisan au travail
├── maison-renovee.jpg        # Maison renovee
├── step1-selection.jpg       # Etape 1
├── step2-eligibility.jpg     # Etape 2
├── step3-artisan.jpg         # Etape 3
├── card-pac.jpg              # Card PAC
├── card-isolation.jpg        # Card isolation
├── card-solaire.jpg          # Card solaire
├── hero-solaire.jpg          # Hero page solaire
├── hero-isolation.jpg        # Hero page isolation
├── hero-pac.jpg              # Hero page PAC
├── icon-mpr.jpg              # Icone MaPrimeRenov
├── icon-cee.jpg              # Icone CEE
└── icon-anah.jpg             # Icone Anah
```

---

## STRATEGIE MAILLAGE INTERNE

### Principe
Chaque page doit :
1. **Mentionner** les autres pages avec des liens contextuels
2. **Pousser** vers le formulaire (CTA multiples)
3. **Creer un parcours** logique de decouverte

### Matrice de liens croises

| Page | Liens vers | Logique |
|------|------------|---------|
| **index.html** | Toutes les pages | Hub central |
| **panneaux-solaires** | PAC, Isolation, MPR, CEE | "Cumulez avec..." |
| **isolation** | PAC, Solaire, MPR, CEE, Anah | "Completez par..." |
| **pompe-a-chaleur** | Isolation, Solaire, MPR, CEE | "Associez a..." |
| **maprimerenov** | CEE, Anah, Solaire, PAC, Isol | "Cumulable avec..." |
| **prime-cee** | MPR, Anah, tous dispositifs | "En plus de MPR..." |
| **anah** | MPR, CEE, tous dispositifs | "Alternative a..." |

### Sections de maillage a ajouter sur chaque page

#### 1. Encart "A decouvrir aussi" (milieu de page)
```html
<section class="decouvrir-aussi">
    <h3>Completez votre projet</h3>
    <div class="liens-cards">
        <a href="isolation.html" class="lien-card">
            <img src="images/card-isolation.jpg">
            <span>Isolation : jusqu'a 90€/m2 d'aides</span>
        </a>
        <a href="maprimerenov.html" class="lien-card">
            <img src="images/icon-mpr.jpg">
            <span>MaPrimeRenov : le guide complet</span>
        </a>
    </div>
</section>
```

#### 2. Encart "Cumulez les aides" (sur pages dispositifs)
```html
<section class="cumul-aides">
    <h3>Maximisez vos aides</h3>
    <p>Ce dispositif est eligible a :</p>
    <div class="aides-badges">
        <a href="maprimerenov.html">MaPrimeRenov' : 5 000€</a>
        <a href="prime-cee.html">Prime CEE : 4 000€</a>
        <a href="anah.html">Anah : jusqu'a 70 000€</a>
    </div>
    <a href="formulaire.html" class="btn-cta">Calculer mon cumul d'aides</a>
</section>
```

#### 3. Encart "Travaux eligibles" (sur pages aides)
```html
<section class="travaux-eligibles">
    <h3>Travaux finances par cette aide</h3>
    <div class="travaux-grid">
        <a href="pompe-a-chaleur.html">
            <i class="fas fa-fan"></i>
            Pompe a chaleur : 3-11k€
        </a>
        <a href="isolation.html">
            <i class="fas fa-home"></i>
            Isolation : 40-75€/m2
        </a>
        <a href="panneaux-solaires.html">
            <i class="fas fa-solar-panel"></i>
            Solaire thermique : 2-4k€
        </a>
    </div>
</section>
```

#### 4. Bandeau sticky CTA (toutes pages)
```html
<div class="sticky-cta-bottom">
    <span>Vous etes eligible jusqu'a <strong>11 000€</strong> d'aides</span>
    <a href="formulaire.html">Tester mon eligibilite</a>
</div>
```

### Parcours utilisateur type

```
Entree: Google/Pub
    ↓
Landing (index.html)
    ↓ CTA principal
Formulaire ← ← ← ← ← ← ← ← ←
    ↑                         ↑
    ← Page dispositif ← ← ← ← ↑
         ↓ lien "aides"       ↑
    ← Page aide ← ← ← ← ← ← ←
         ↓ CTA
    → Formulaire → Merci
```

### Regles de maillage

1. **Minimum 3 liens internes** par page (hors nav)
2. **CTA formulaire** visible sans scroll (above the fold)
3. **Sticky CTA mobile** en bas de page
4. **Liens contextuels** dans le contenu (pas juste footer)
5. **Montants d'aides** toujours affiches (incitation)

---

## PLAN MULTI-AGENT V5 (5 Agents)

### Agent 1 : Recherche Images (Perplexity)
**MCP** : `mcp__perplexity__perplexity_search`

Rechercher des idees d'images pour sites renovation energie :
- "landing page renovation energetique images exemples"
- "site travaux maison photos professionnelles conversion"
- "images avant apres renovation thermique"
- "photos installateurs panneaux solaires travail"
- "visuels marketing aides renovation 2025"

**Output** : Liste de 15-20 prompts d'images a generer

---

### Agent 2 : Generation Images IA (Fal.ai)
**MCP** : `mcp__fal-ai__run_model`

**IMPORTANT** : Utiliser `run_model` PAS `generate_image`

Generer ~15 nouvelles images selon la liste de l'Agent 1 :

#### Categorie HUMAINS
```
- Couple senior souriant devant maison avec panneaux solaires
- Famille avec enfants dans salon chaud et confortable
- Artisan RGE installant pompe a chaleur (gros plan)
- Conseiller energie expliquant documents a client
- Technicien sur toit installant panneaux (vue drone)
```

#### Categorie DEMONSTRATIONS
```
- Before/after facade maison (isolation exterieure)
- Thermographie maison (rouge = pertes chaleur)
- Schema PAC air-eau simplifie (infographie)
- Toiture avec et sans panneaux solaires (split)
- Facture energie avant/apres travaux
```

#### Categorie CONTEXTE
```
- Maison francaise typique avec jardin
- Interieur cosy hiver (feu, couverture, confort)
- Document officiel MaPrimeRenov (illustration)
- Artisan RGE avec badge certification
- Maison passive moderne eco-responsable
```

**Workflow** :
```javascript
mcp__fal-ai__run_model({
    model_id: "fal-ai/flux/dev",
    input: {
        prompt: "[PROMPT]",
        num_images: 1,
        image_size: "landscape_16_9" // ou "square"
    }
})
// Puis : curl -o "images/[nom].jpg" "[URL]"
```

---

### Agent 3 : Integration Images (Pas de MCP)
**Outils** : Read, Write, Edit

Pour chaque page, ajouter les nouvelles images :

#### index.html
- Section hero : image famille/couple
- Section avantages : icones ou petites images
- Section temoignages : photos clients
- Section reassurance : badges, certifications

#### Pages dispositifs (solaire, isolation, pac)
- Hero : image contextuelle du dispositif
- Section avantages : avant/apres ou demonstrations
- Section processus : photos artisans au travail
- FAQ : illustrations explicatives

#### Pages aides (mpr, cee, anah)
- Hero : illustration officielle/gouvernementale
- Section baremes : infographies
- Section demarches : photos conseiller/documents

---

### Agent 4 : Maillage Interne (Pas de MCP)
**Outils** : Read, Write, Edit

Ajouter sur CHAQUE page :

#### 1. Section "Completez votre projet" (apres hero ou milieu)
- 2-3 cards vers autres pages pertinentes
- Avec images et montants d'aides

#### 2. Section "Cumulez les aides" (pages dispositifs)
- Badges cliquables vers pages aides
- Montants cumules affiches
- CTA "Calculer mon cumul"

#### 3. Section "Travaux eligibles" (pages aides)
- Grid de liens vers dispositifs
- Icones + montants

#### 4. Sticky CTA mobile (toutes pages)
- Bandeau fixe en bas
- Montant accrocheur + bouton formulaire

#### 5. Liens contextuels dans le texte
- Dans les paragraphes existants
- Ex: "Cumulez avec la [Prime CEE](prime-cee.html)"

**Verification** : Chaque page doit avoir min 5 liens internes + 2 CTA formulaire

---

### Agent 5 : Tests et Deploy (Playwright + Vercel)
**MCP** : `mcp__playwright__*`, `mcp__vercel__*`

1. Tester les 9 pages enrichies
2. Verifier chargement images
3. Screenshots avant/apres
4. Commit + Push + Deploy

---

## EXECUTION RECOMMANDEE

### Phase 1 (parallele)
- Agent 1 : Recherche Perplexity → liste prompts images
- Agent 2 : Generer images (peut commencer avec prompts de base)

### Phase 2 (parallele)
- Agent 3 : Integrer images sur les 9 pages
- Agent 4 : Ajouter maillage interne sur les 9 pages

### Phase 3
- Agent 5 : Tests + Deploy

---

## SPECIFICATIONS IMAGES

### Formats
- **Hero** : landscape_16_9 (1024x576)
- **Cards** : square (512x512 ou 1024x1024)
- **Icones** : square petit (256x256)

### Style
- Photorealiste professionnel
- Couleurs chaudes et accueillantes
- Lumiere naturelle
- Contexte francais (maisons francaises, pas US)
- Humains : diversite, sourires, confiance

### Prompts types
```
"[SUJET], professional photography, warm lighting, French house,
happy family, realistic, 4k quality, clean aesthetic"
```

---

## DONNEES DISPONIBLES

Le fichier `DONNEES-2025.md` contient :
- Baremes MaPrimeRenov 2025 (4 profils)
- Montants CEE par travaux
- Prix panneaux solaires + primes
- Prix PAC + aides cumulables
- Prix isolation ITE + aides
- Analyse site concurrent
- Synthese donnees cles

**Utiliser ces donnees pour** :
- Verifier coherence des montants affiches
- Ajouter des chiffres manquants
- Creer des infographies avec vrais montants

---

## CHECKLIST V5

### Phase 1 - Recherche & Generation
- [ ] Liste 15-20 prompts images creee
- [ ] 15+ images generees et telechargees
- [ ] Nommage coherent (ex: famille-confort.jpg, artisan-pac.jpg)

### Phase 2 - Integration Images
- [ ] index.html : 3-5 nouvelles images
- [ ] panneaux-solaires.html : images
- [ ] isolation.html : images
- [ ] pompe-a-chaleur.html : images
- [ ] maprimerenov.html : images
- [ ] prime-cee.html : images
- [ ] anah.html : images

### Phase 2 - Maillage Interne
- [ ] index.html : liens vers toutes pages
- [ ] panneaux-solaires.html : section cumul aides + liens dispositifs
- [ ] isolation.html : section cumul aides + liens dispositifs
- [ ] pompe-a-chaleur.html : section cumul aides + liens dispositifs
- [ ] maprimerenov.html : section travaux eligibles + liens aides
- [ ] prime-cee.html : section travaux eligibles + liens aides
- [ ] anah.html : section travaux eligibles + liens aides
- [ ] Sticky CTA mobile sur toutes les pages
- [ ] Min 5 liens internes par page

### Phase 3 - Deploy
- [ ] Tests navigation OK
- [ ] Tests liens internes OK
- [ ] Git commit + push
- [ ] Vercel deploy
- [ ] Site live verifie

---

## COMMANDE POUR LANCER

```
Lis PROMPT-V5-ENRICHISSEMENT.md dans eligibilite-clone et execute :

Phase 1 (parallele) :
- Agent 1 : Recherche Perplexity idees images
- Agent 2 : Genere 15+ images Fal.ai

Phase 2 (parallele, apres Phase 1) :
- Agent 3 : Integre images (pas de MCP)
- Agent 4 : Ajoute maillage interne (pas de MCP)

Phase 3 :
- Agent 5 : Tests Playwright + Deploy Vercel

Objectif : Toutes les pages doivent pousser vers le formulaire.
```

---

*Prompt V5 - Cree le 02/12/2025*
*Objectif : Enrichissement visuel + maillage pour conversion maximale*
