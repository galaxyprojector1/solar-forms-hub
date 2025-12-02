# PROMPT V4 - Eligibilite Clone - 6 Nouvelles Pages

## OBJECTIF GLOBAL

Transformer eligibilite-clone en site complet avec :
- 3 pages **Dispositifs** (solaire, isolation, PAC)
- 3 pages **Aides** (MaPrimeRenov, CEE, Anah)
- Navigation **dropdown** sur toutes les pages
- **Images IA** professionnelles
- Design inspire de **primerenovation-en-ligne.com**

**URL actuelle** : https://solar-forms-hub.vercel.app/multi-sites/eligibilite-clone/

---

## STRUCTURE FINALE

```
multi-sites/eligibilite-clone/
├── index.html              # Landing principale (EXISTE - A MODIFIER)
├── formulaire.html         # Formulaire 5 etapes (EXISTE - A MODIFIER)
├── merci.html              # Confirmation (EXISTE - A MODIFIER)
│
├── panneaux-solaires.html  # A CREER
├── isolation.html          # A CREER
├── pompe-a-chaleur.html    # A CREER
│
├── maprimerenov.html       # A CREER
├── prime-cee.html          # A CREER
├── anah.html               # A CREER
│
└── images/
    ├── [existantes]        # 15 images actuelles
    ├── hero-solaire.jpg    # A GENERER
    ├── hero-isolation.jpg  # A GENERER
    ├── hero-pac.jpg        # A GENERER
    ├── icon-mpr.jpg        # A GENERER
    ├── icon-cee.jpg        # A GENERER
    └── icon-anah.jpg       # A GENERER
```

---

## PLAN MULTI-AGENT (6 AGENTS)

### REPARTITION DES MCP PAR AGENT

| Agent | Mission | MCP Requis | Outils Base |
|-------|---------|------------|-------------|
| **Agent 1** | Recherche concurrents | ✅ Perplexity, Playwright | Read |
| **Agent 2** | Generation images | ✅ Fal.ai | Bash (curl) |
| **Agent 3** | Pages Dispositifs (x3) | ❌ Aucun | Read, Write, Edit |
| **Agent 4** | Pages Aides (x3) | ❌ Aucun | Read, Write, Edit |
| **Agent 5** | Navigation + MAJ pages | ❌ Aucun | Read, Write, Edit |
| **Agent 6** | Tests + Deploiement | ✅ Playwright, Vercel, GitHub | Bash |

**IMPORTANT** : Les agents 3, 4, 5 n'ont PAS besoin de MCP = contexte optimise !

---

## AGENT 1 : Recherche & Analyse

**MCP requis** : `mcp__perplexity__perplexity_search`, `mcp__playwright__*`

### Mission

1. **Rechercher les sites concurrents** pour s'inspirer du contenu :

```
mcp__perplexity__perplexity_search({
    query: "MaPrimeRenov 2025 montants baremes conditions eligibilite"
})

mcp__perplexity__perplexity_search({
    query: "Prime CEE certificats economies energie montants 2025"
})

mcp__perplexity__perplexity_search({
    query: "Aides Anah 2025 MaPrimeRenov Serenite conditions"
})

mcp__perplexity__perplexity_search({
    query: "Prix installation panneaux solaires 2025 aides prime autoconsommation"
})

mcp__perplexity__perplexity_search({
    query: "Prix pompe a chaleur air eau 2025 aides MaPrimeRenov"
})

mcp__perplexity__perplexity_search({
    query: "Prix isolation thermique exterieure ITE 2025 aides m2"
})
```

2. **Analyser le site de reference** primerenovation-en-ligne.com :

```
mcp__playwright__browser_navigate({ url: "https://primerenovation-en-ligne.com" })
mcp__playwright__browser_snapshot()
mcp__playwright__browser_take_screenshot({ filename: "concurrent-home.png" })

mcp__playwright__browser_navigate({ url: "https://primerenovation-en-ligne.com/new/maprimerenov" })
mcp__playwright__browser_snapshot()
mcp__playwright__browser_take_screenshot({ filename: "concurrent-mpr.png" })
```

3. **Creer un rapport** avec les infos cles :

Ecrire dans `multi-sites/eligibilite-clone/RECHERCHE-V4.md` :
- Montants aides 2025 (MPR, CEE, etc.)
- Structure des pages concurrentes
- Contenus a reprendre
- Baremes par revenus

### Output attendu

Fichier `RECHERCHE-V4.md` avec toutes les donnees a jour pour les autres agents.

---

## AGENT 2 : Generation Images IA

**MCP requis** : `mcp__fal-ai__run_model`

### Mission

Generer 6 images professionnelles pour les nouvelles pages.

**IMPORTANT** : Utiliser `run_model` PAS `generate_image` (bug connu)

### Images a generer

#### 1. hero-solaire.jpg (Hero page solaire)
```javascript
mcp__fal-ai__run_model({
    model_id: "fal-ai/flux/dev",
    input: {
        prompt: "Modern French house rooftop with solar panels installation, blue sky, sunny day, professional real estate photography, wide angle, clean aesthetic, 4k quality",
        num_images: 1,
        image_size: "landscape_16_9"
    }
})
// Puis: curl -o "multi-sites/eligibilite-clone/images/hero-solaire.jpg" "URL"
```

#### 2. hero-isolation.jpg (Hero page isolation)
```javascript
mcp__fal-ai__run_model({
    model_id: "fal-ai/flux/dev",
    input: {
        prompt: "French house exterior wall insulation work in progress, worker installing thermal insulation panels, professional construction photography, bright daylight, modern home",
        num_images: 1,
        image_size: "landscape_16_9"
    }
})
```

#### 3. hero-pac.jpg (Hero page PAC)
```javascript
mcp__fal-ai__run_model({
    model_id: "fal-ai/flux/dev",
    input: {
        prompt: "Modern heat pump unit installed outside French house, white air-to-water heat pump, garden background, professional HVAC photography, clean installation, sunny day",
        num_images: 1,
        image_size: "landscape_16_9"
    }
})
```

#### 4. icon-mpr.jpg (Icone MaPrimeRenov)
```javascript
mcp__fal-ai__run_model({
    model_id: "fal-ai/flux/dev",
    input: {
        prompt: "French government building facade with tricolor flag, official administrative building, blue sky, professional architecture photography, clean modern style",
        num_images: 1,
        image_size: "square"
    }
})
```

#### 5. icon-cee.jpg (Icone Prime CEE)
```javascript
mcp__fal-ai__run_model({
    model_id: "fal-ai/flux/dev",
    input: {
        prompt: "Energy efficiency certificate document with green checkmark, official paper document, professional flat lay photography, clean white background, business style",
        num_images: 1,
        image_size: "square"
    }
})
```

#### 6. icon-anah.jpg (Icone Anah)
```javascript
mcp__fal-ai__run_model({
    model_id: "fal-ai/flux/dev",
    input: {
        prompt: "French family house renovation concept, before and after renovation, split image, home improvement, professional real estate photography",
        num_images: 1,
        image_size: "square"
    }
})
```

### Workflow

Pour chaque image :
1. Executer `run_model` avec le prompt
2. Recuperer l'URL dans la reponse
3. Telecharger avec curl :
```bash
curl -o "C:/Users/yohann/Downloads/solar-forms-hub/solar-forms-hub/multi-sites/eligibilite-clone/images/[nom].jpg" "[URL]"
```
4. Verifier que l'image existe

### Output attendu

6 images dans le dossier `images/` :
- hero-solaire.jpg
- hero-isolation.jpg
- hero-pac.jpg
- icon-mpr.jpg
- icon-cee.jpg
- icon-anah.jpg

---

## AGENT 3 : Pages Dispositifs (x3)

**MCP requis** : ❌ Aucun (contexte optimise)

### Mission

Creer 3 pages HTML completes pour les dispositifs/travaux.

### Pre-requis

1. Lire `index.html` pour copier le style header/footer
2. Lire `RECHERCHE-V4.md` pour les donnees a jour (si disponible)
3. Utiliser les images generees par Agent 2 (si disponibles)

### Page 1 : panneaux-solaires.html

**Structure** :
```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Panneaux Solaires 2025 : Aides et Installation - Eligibilite.fr</title>
    <meta name="description" content="Installation panneaux solaires : jusqu'a 2340€ de prime autoconsommation. Devis gratuit, artisans RGE certifies.">
    <!-- Memes CDN que index.html -->
</head>
<body>
    <!-- Header avec dropdown (voir Agent 5) -->

    <!-- Hero Solaire -->
    <section class="hero-page" style="background: linear-gradient(135deg, #FFF7ED 0%, #FFEDD5 100%);">
        <div class="container">
            <div class="hero-content">
                <span class="badge-orange">Energie Solaire</span>
                <h1>Panneaux Solaires : Produisez votre propre electricite</h1>
                <p class="subtitle">Jusqu'a <strong>2 340€</strong> de prime + autoconsommation gratuite</p>
                <ul class="hero-features">
                    <li><i class="fas fa-check"></i> Reduction facture jusqu'a 70%</li>
                    <li><i class="fas fa-check"></i> Revenus EDF OA garantis 20 ans</li>
                    <li><i class="fas fa-check"></i> Installation en 1-2 jours</li>
                </ul>
                <a href="formulaire.html?type=solaire" class="btn-orange">
                    Estimer mes aides solaires <i class="fas fa-arrow-right"></i>
                </a>
            </div>
            <div class="hero-image">
                <img src="images/hero-solaire.jpg" alt="Maison avec panneaux solaires">
            </div>
        </div>
    </section>

    <!-- Section Avantages (4 cards) -->
    <section class="avantages-section">
        <h2>Pourquoi passer au solaire ?</h2>
        <div class="avantages-grid">
            <div class="avantage-card">
                <i class="fas fa-piggy-bank"></i>
                <h3>Economies jusqu'a 70%</h3>
                <p>Reduisez votre facture d'electricite en produisant votre propre energie.</p>
            </div>
            <div class="avantage-card">
                <i class="fas fa-hand-holding-usd"></i>
                <h3>Revenus garantis</h3>
                <p>Revendez votre surplus a EDF OA : 0.13€/kWh pendant 20 ans.</p>
            </div>
            <div class="avantage-card">
                <i class="fas fa-leaf"></i>
                <h3>Ecologique</h3>
                <p>Energie 100% renouvelable, reduisez votre empreinte carbone.</p>
            </div>
            <div class="avantage-card">
                <i class="fas fa-home"></i>
                <h3>Plus-value immobiliere</h3>
                <p>Valorisez votre bien de +6% avec une installation solaire.</p>
            </div>
        </div>
    </section>

    <!-- Section Aides disponibles -->
    <section class="aides-section">
        <h2>Les aides pour le solaire en 2025</h2>
        <div class="aides-grid">
            <div class="aide-card">
                <h3>Prime Autoconsommation</h3>
                <p class="montant">260€ a 500€/kWc</p>
                <p>Versee sur 5 ans par EDF OA</p>
            </div>
            <div class="aide-card">
                <h3>TVA Reduite</h3>
                <p class="montant">10% au lieu de 20%</p>
                <p>Pour les installations ≤ 3kWc</p>
            </div>
            <div class="aide-card">
                <h3>Eco-PTZ</h3>
                <p class="montant">Jusqu'a 15 000€</p>
                <p>Pret a taux zero sur 15 ans</p>
            </div>
            <div class="aide-card highlight">
                <h3>Total Aides</h3>
                <p class="montant">Jusqu'a 2 340€</p>
                <p>Pour une installation 3kWc</p>
            </div>
        </div>
    </section>

    <!-- Section Comment ca marche -->
    <section class="etapes-section">
        <h2>Comment ca marche ?</h2>
        <div class="etapes-timeline">
            <div class="etape">
                <span class="numero">1</span>
                <h3>Etude gratuite</h3>
                <p>Un conseiller analyse votre toiture et votre consommation.</p>
            </div>
            <div class="etape">
                <span class="numero">2</span>
                <h3>Devis personnalise</h3>
                <p>Artisan RGE certifie vous propose une solution adaptee.</p>
            </div>
            <div class="etape">
                <span class="numero">3</span>
                <h3>Installation rapide</h3>
                <p>Pose en 1-2 jours, mise en service immediate.</p>
            </div>
        </div>
    </section>

    <!-- Section FAQ -->
    <section class="faq-section">
        <h2>Questions frequentes</h2>
        <div class="faq-list">
            <div class="faq-item">
                <div class="faq-question">
                    <h4>Combien coute une installation solaire ?</h4>
                    <i class="fas fa-plus"></i>
                </div>
                <div class="faq-answer">
                    <p>Une installation de 3kWc coute entre 7 000€ et 10 000€ avant aides. Apres deduction de la prime autoconsommation, comptez environ 6 000€ a 8 000€.</p>
                </div>
            </div>
            <div class="faq-item">
                <div class="faq-question">
                    <h4>Quelle surface de toit faut-il ?</h4>
                    <i class="fas fa-plus"></i>
                </div>
                <div class="faq-answer">
                    <p>Comptez environ 6m2 par kWc. Pour une installation standard de 3kWc, il faut environ 18m2 de toiture orientee sud.</p>
                </div>
            </div>
            <div class="faq-item">
                <div class="faq-question">
                    <h4>Quelle est la duree de vie des panneaux ?</h4>
                    <i class="fas fa-plus"></i>
                </div>
                <div class="faq-answer">
                    <p>Les panneaux solaires sont garantis 25 ans et ont une duree de vie de 30 a 40 ans. Leur rendement diminue d'environ 0.5% par an.</p>
                </div>
            </div>
            <div class="faq-item">
                <div class="faq-question">
                    <h4>Puis-je revendre mon electricite ?</h4>
                    <i class="fas fa-plus"></i>
                </div>
                <div class="faq-answer">
                    <p>Oui ! Avec un contrat EDF OA, vous revendez votre surplus a 0.13€/kWh pendant 20 ans. C'est garanti par l'Etat.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- CTA Final -->
    <section class="cta-section">
        <div class="container">
            <h2>Pret a produire votre propre electricite ?</h2>
            <p>Verifiez votre eligibilite en 2 minutes</p>
            <a href="formulaire.html?type=solaire" class="btn-orange btn-large">
                Je calcule mes aides solaires <i class="fas fa-arrow-right"></i>
            </a>
        </div>
    </section>

    <!-- Footer (copier de index.html) -->
    <footer class="footer">...</footer>
</body>
</html>
```

### Page 2 : isolation.html

**Couleur accent** : Vert (#10B981)
**Titre** : "Isolation Thermique : Reduisez vos pertes de chaleur"
**Sous-titre** : "Jusqu'a 75€/m2 d'aides"
**Lien** : `formulaire.html?type=isolation`

**Contenu specifique** :
- Types : Combles (30% pertes), Murs ITE (25%), Sols (10%), Fenetres (15%)
- Aides : MPR 15-75€/m2, CEE 10-25€/m2, TVA 5.5%, Eco-PTZ 30k€
- FAQ : Priorisation, ITE vs ITI, ROI, cumul aides

### Page 3 : pompe-a-chaleur.html

**Couleur accent** : Bleu (#2563EB)
**Titre** : "Pompe a Chaleur : Chauffez pour 3x moins cher"
**Sous-titre** : "Jusqu'a 11 000€ d'aides"
**Lien** : `formulaire.html?type=pac`

**Contenu specifique** :
- Types : Air-Air, Air-Eau, Geothermique
- Aides : MPR 2-5k€, CEE 2.5-4k€, TVA 5.5%, Eco-PTZ 15k€
- Avantages : COP 3-5, economies 50-70%, ecologique
- FAQ : Choix PAC, bruit, entretien, duree vie

### Output attendu

3 fichiers HTML complets :
- panneaux-solaires.html (< 80KB)
- isolation.html (< 80KB)
- pompe-a-chaleur.html (< 80KB)

---

## AGENT 4 : Pages Aides (x3)

**MCP requis** : ❌ Aucun (contexte optimise)

### Mission

Creer 3 pages HTML pour les differentes aides financieres.

### Pre-requis

1. Lire `index.html` pour le style
2. Lire `RECHERCHE-V4.md` pour les baremes officiels 2025

### Page 1 : maprimerenov.html

**Structure** :
```html
<section class="hero-aide">
    <div class="aide-logo">
        <img src="images/icon-mpr.jpg" alt="MaPrimeRenov">
    </div>
    <h1>MaPrimeRenov' 2025 : Le Guide Complet</h1>
    <p>L'aide principale de l'Etat pour financer vos travaux de renovation energetique</p>
</section>

<section class="baremes-section">
    <h2>Montants selon vos revenus</h2>
    <div class="baremes-table">
        <!-- Tableau avec 4 profils : Bleu, Jaune, Violet, Rose -->
        <!-- Montants pour PAC, Isolation, Fenetres, etc. -->
    </div>
</section>

<section class="travaux-eligibles">
    <h2>Travaux eligibles</h2>
    <!-- Liste : PAC, Isolation, Chauffe-eau solaire, VMC, Fenetres... -->
</section>

<section class="conditions">
    <h2>Conditions d'eligibilite</h2>
    <ul>
        <li>Etre proprietaire (occupant ou bailleur)</li>
        <li>Logement construit depuis plus de 15 ans</li>
        <li>Travaux realises par un artisan RGE</li>
        <li>Residence principale en France</li>
    </ul>
</section>

<section class="demarches">
    <h2>Comment obtenir MaPrimeRenov' ?</h2>
    <!-- 5 etapes : Compte, Devis, Demande, Travaux, Prime -->
</section>
```

**Baremes 2025 (a integrer)** :

| Profil | Revenus 1 pers | PAC Air-Eau | Isolation Murs | Fenetres |
|--------|----------------|-------------|----------------|----------|
| Bleu (tres modeste) | < 17 009€ | 5 000€ | 75€/m2 | 100€/fen |
| Jaune (modeste) | < 21 805€ | 4 000€ | 60€/m2 | 80€/fen |
| Violet (intermediaire) | < 30 549€ | 3 000€ | 40€/m2 | 40€/fen |
| Rose (aise) | > 30 549€ | 0€ | 0€ | 0€ |

### Page 2 : prime-cee.html

**Titre** : "Prime CEE : L'Aide des Fournisseurs d'Energie"
**Description** : "Certificats d'Economies d'Energie - Cumulable avec MaPrimeRenov'"

**Contenu** :
- Explication du dispositif CEE
- Montants par travaux (PAC, isolation, etc.)
- Liste des fournisseurs (EDF, Engie, Total, etc.)
- Conditions (logement > 2 ans, artisan RGE)
- Cumul avec autres aides

### Page 3 : anah.html

**Titre** : "Aides Anah : MaPrimeRenov' Serenite"
**Description** : "Pour les renovations globales des menages modestes"

**Contenu** :
- Programme Serenite (35% des travaux, plafond 30k€)
- Conditions (gain energetique 35% min)
- Accompagnement Mon Accompagnateur Renov'
- Autres aides Anah (Habiter Mieux, Loc'Avantages)

### Output attendu

3 fichiers HTML complets :
- maprimerenov.html (< 80KB)
- prime-cee.html (< 80KB)
- anah.html (< 80KB)

---

## AGENT 5 : Navigation & MAJ Pages Existantes

**MCP requis** : ❌ Aucun (contexte optimise)

### Mission

1. Ajouter le menu dropdown sur TOUTES les pages
2. Modifier les pages existantes (index, formulaire, merci)
3. Ajouter le menu sur les nouvelles pages

### CSS Dropdown a ajouter

```css
/* ========== DROPDOWN MENU ========== */
.nav-menu .dropdown {
    position: relative;
}

.nav-menu .dropdown > a {
    display: flex;
    align-items: center;
    gap: 5px;
}

.dropdown-menu {
    position: absolute;
    top: 100%;
    left: 50%;
    transform: translateX(-50%) translateY(10px);
    background: var(--white);
    border-radius: 12px;
    box-shadow: 0 10px 40px rgba(0,0,0,0.15);
    padding: 12px 0;
    min-width: 240px;
    opacity: 0;
    visibility: hidden;
    transition: all 0.3s ease;
    z-index: 100;
    list-style: none;
}

.dropdown:hover .dropdown-menu {
    opacity: 1;
    visibility: visible;
    transform: translateX(-50%) translateY(0);
}

.dropdown-menu li a {
    display: flex;
    align-items: center;
    gap: 12px;
    padding: 12px 20px;
    color: var(--text-dark);
    font-weight: 500;
    transition: all 0.2s;
}

.dropdown-menu li a:hover {
    background: var(--gray-light);
    color: var(--blue-primary);
}

.dropdown-menu li a i {
    width: 20px;
    color: var(--orange);
}

/* Mobile dropdown */
@media (max-width: 768px) {
    .dropdown-menu {
        position: static;
        transform: none;
        box-shadow: none;
        max-height: 0;
        overflow: hidden;
        padding: 0;
        background: rgba(255,255,255,0.1);
        border-radius: 8px;
        margin-top: 10px;
    }

    .dropdown.active .dropdown-menu {
        max-height: 300px;
        padding: 10px 0;
        opacity: 1;
        visibility: visible;
    }

    .dropdown-menu li a {
        color: var(--white);
        padding: 10px 20px;
    }
}
```

### HTML Navigation a remplacer

```html
<nav class="nav">
    <ul class="nav-menu">
        <li class="dropdown">
            <a href="#">Les dispositifs <i class="fas fa-chevron-down dropdown-icon"></i></a>
            <ul class="dropdown-menu">
                <li><a href="panneaux-solaires.html"><i class="fas fa-solar-panel"></i> Panneaux solaires</a></li>
                <li><a href="isolation.html"><i class="fas fa-home"></i> Isolation thermique</a></li>
                <li><a href="pompe-a-chaleur.html"><i class="fas fa-fan"></i> Pompe a chaleur</a></li>
            </ul>
        </li>
        <li class="dropdown">
            <a href="#">Les aides <i class="fas fa-chevron-down dropdown-icon"></i></a>
            <ul class="dropdown-menu">
                <li><a href="maprimerenov.html"><i class="fas fa-landmark"></i> MaPrimeRenov'</a></li>
                <li><a href="prime-cee.html"><i class="fas fa-certificate"></i> Prime CEE</a></li>
                <li><a href="anah.html"><i class="fas fa-hands-helping"></i> Aides Anah</a></li>
            </ul>
        </li>
        <li><a href="index.html#faq">FAQ</a></li>
    </ul>
    <a href="formulaire.html" class="btn-header">
        Je teste mon eligibilite
        <i class="fas fa-arrow-right"></i>
    </a>
</nav>
```

### JS Mobile Toggle

```javascript
// Dropdown toggle mobile
document.querySelectorAll('.dropdown > a').forEach(link => {
    link.addEventListener('click', function(e) {
        if (window.innerWidth <= 768) {
            e.preventDefault();
            this.parentElement.classList.toggle('active');
        }
    });
});
```

### Fichiers a modifier

1. **index.html** : Remplacer nav-menu + ajouter CSS dropdown
2. **formulaire.html** : Ajouter navigation complete dans header
3. **merci.html** : Ajouter navigation complete
4. **Nouvelles pages** : S'assurer que toutes ont le meme header

### Output attendu

- 3 fichiers existants modifies avec dropdown
- Navigation coherente sur les 9 pages

---

## AGENT 6 : Tests & Deploiement

**MCP requis** : `mcp__playwright__*`, `mcp__vercel__*`, `mcp__github__*`

### Mission

1. Tester toutes les pages
2. Prendre des screenshots
3. Deployer sur Vercel

### Tests Navigation

```javascript
// Tester chaque page
const pages = [
    'index.html',
    'formulaire.html',
    'merci.html',
    'panneaux-solaires.html',
    'isolation.html',
    'pompe-a-chaleur.html',
    'maprimerenov.html',
    'prime-cee.html',
    'anah.html'
];

// Pour chaque page :
mcp__playwright__browser_navigate({ url: `file:///C:/Users/yohann/Downloads/solar-forms-hub/solar-forms-hub/multi-sites/eligibilite-clone/${page}` })
mcp__playwright__browser_snapshot()
// Verifier : header present, dropdown fonctionne, liens OK
```

### Tests Dropdown

```javascript
// Hover sur "Les dispositifs"
mcp__playwright__browser_hover({ element: "Les dispositifs dropdown", ref: "[ref dropdown]" })
mcp__playwright__browser_snapshot()
// Verifier : sous-menu visible avec 3 liens
```

### Screenshots a prendre

1. `v4-index-desktop.png` - Page accueil avec dropdown
2. `v4-solaire-desktop.png` - Page solaire
3. `v4-mpr-desktop.png` - Page MaPrimeRenov
4. `v4-dropdown-open.png` - Menu dropdown ouvert
5. `v4-mobile-menu.png` - Menu mobile

### Deploiement

```bash
# Git
git add .
git commit -m "Eligibilite Clone V4: 6 nouvelles pages + navigation dropdown

Nouvelles pages dispositifs:
- panneaux-solaires.html : Guide complet solaire + aides
- isolation.html : Types d'isolation + aides
- pompe-a-chaleur.html : Guide PAC + aides

Nouvelles pages aides:
- maprimerenov.html : Baremes 2025 complets
- prime-cee.html : Guide CEE
- anah.html : Aides Anah Serenite

Ameliorations:
- Navigation dropdown sur toutes les pages
- 6 nouvelles images IA
- SEO optimise par page
- Mobile responsive

Generated with Claude Code"

git push

# Vercel
npx vercel --prod --yes
```

### Verification Production

```javascript
mcp__playwright__browser_navigate({ url: "https://solar-forms-hub.vercel.app/multi-sites/eligibilite-clone/" })
mcp__playwright__browser_snapshot()
// Verifier : site live, dropdown fonctionne

mcp__playwright__browser_navigate({ url: "https://solar-forms-hub.vercel.app/multi-sites/eligibilite-clone/panneaux-solaires.html" })
// Verifier : nouvelle page accessible
```

### Output attendu

- Rapport de tests dans `TESTS-V4-REPORT.md`
- Screenshots dans `.playwright-mcp/`
- Site deploye et fonctionnel

---

## EXECUTION DU PROMPT

### Methode Recommandee : 3 Phases

**PHASE 1 - Recherche & Images** (Agents 1 et 2 en parallele)
```
Lance Agent 1 (Perplexity + Playwright) : Recherche concurrents et donnees 2025
Lance Agent 2 (Fal.ai) : Generation des 6 images

Attendre que les deux finissent avant Phase 2.
```

**PHASE 2 - Creation Pages** (Agents 3, 4, 5 en parallele)
```
Lance Agent 3 : Cree panneaux-solaires.html, isolation.html, pompe-a-chaleur.html
Lance Agent 4 : Cree maprimerenov.html, prime-cee.html, anah.html
Lance Agent 5 : Met a jour navigation sur toutes les pages

Ces 3 agents n'ont PAS besoin de MCP = rapides et economes en contexte.
```

**PHASE 3 - Tests & Deploy** (Agent 6)
```
Lance Agent 6 (Playwright + Vercel) : Teste tout et deploie
```

### Commande Complete

```
Lis PROMPT-V4-NOUVELLES-PAGES.md dans eligibilite-clone.

PHASE 1 (parallele) :
- Agent 1 : Recherche avec Perplexity + analyse Playwright
- Agent 2 : Genere 6 images avec Fal.ai

PHASE 2 (parallele, apres Phase 1) :
- Agent 3 : Cree 3 pages dispositifs (pas de MCP)
- Agent 4 : Cree 3 pages aides (pas de MCP)
- Agent 5 : MAJ navigation (pas de MCP)

PHASE 3 (apres Phase 2) :
- Agent 6 : Tests Playwright + Deploy Vercel
```

---

## CHECKLIST FINALE V4

### Phase 1
- [ ] RECHERCHE-V4.md cree avec donnees 2025
- [ ] 6 images IA generees et telechargees

### Phase 2 - Pages Dispositifs
- [ ] panneaux-solaires.html cree
- [ ] isolation.html cree
- [ ] pompe-a-chaleur.html cree

### Phase 2 - Pages Aides
- [ ] maprimerenov.html cree
- [ ] prime-cee.html cree
- [ ] anah.html cree

### Phase 2 - Navigation
- [ ] Dropdown sur index.html
- [ ] Dropdown sur formulaire.html
- [ ] Dropdown sur merci.html
- [ ] Dropdown sur 6 nouvelles pages

### Phase 3
- [ ] Tests OK sur 9 pages
- [ ] Screenshots pris
- [ ] Git commit + push
- [ ] Vercel deploy
- [ ] Site live fonctionne

---

*Prompt V4 - Cree le 02/12/2025*
*Methode multi-agent optimisee pour economie de contexte*
*Reproductible pour futurs projets*
