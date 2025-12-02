# PROMPT COMPLET - Eligibilite Clone V3 Multi-Pages

## MISSION GLOBALE

Transformer `eligibilite-clone` d'une page unique en un site multi-pages professionnel optimise pour la conversion de leads renovation energetique.

**Objectif** : Taux de conversion > 30% (vue formulaire → soumission)

---

## MCP PAR AGENT (OPTIMISATION CONTEXTE)

Chaque agent n'a besoin que de certains outils. Cela economise du contexte !

| Agent | Mission | MCP necessaires | Outils de base |
|-------|---------|-----------------|----------------|
| **Agent 1** | Formulaire | ❌ Aucun | Read, Write, Edit |
| **Agent 2** | Page Merci | ❌ Aucun | Read, Write, Edit |
| **Agent 3** | Landing page | ❌ Aucun | Read, Write, Edit |
| **Agent 4** | Tests visuels | ✅ **Playwright** | Read, Bash |
| **Agent 5** | Deploiement | ✅ **Vercel**, **GitHub** | Bash, Read |
| **Agent 6** | Images IA | ✅ **Fal.ai** | Bash (curl) |

### Instructions pour chaque agent

**Agents 1, 2, 3** (code pur) :
```
Cet agent n'a PAS besoin de MCP. Utilise uniquement Read, Write, Edit, Glob, Grep.
```

**Agent 4** (tests) :
```
Utilise mcp__playwright pour :
- browser_navigate vers les pages
- browser_snapshot pour verifier le rendu
- browser_take_screenshot pour documenter
```

**Agent 5** (deploy) :
```
Utilise mcp__vercel pour :
- deploy_to_vercel
- list_deployments (verification)

Utilise mcp__github pour :
- Verifier le push si besoin
```

**Agent 6** (images) :
```
Utilise mcp__fal-ai__run_model avec :
- model_id: "fal-ai/flux/dev"
- input: {"prompt": "...", "num_images": 1, "image_size": "landscape_16_9"}

Puis telecharge avec Bash:
curl -o "chemin/images/nom.jpg" "URL_RETOURNEE"
```

---

## CAPTURES D'ECRAN DE REFERENCE

Ces captures montrent le design actuel a conserver/ameliorer :

### Desktop
- `.playwright-mcp/.playwright-mcp/eligibilite-v2-desktop-hero.png` - Hero section
- `.playwright-mcp/.playwright-mcp/eligibilite-v2-formulaire-desktop.png` - Formulaire actuel
- `.playwright-mcp/.playwright-mcp/eligibilite-v2-formulaire-step1.png` - Etape 1

### Mobile
- `.playwright-mcp/.playwright-mcp/eligibilite-v2-mobile-hero.png` - Hero mobile
- `.playwright-mcp/.playwright-mcp/eligibilite-v2-mobile-formulaire.png` - Formulaire mobile

### Site original (inspiration)
- `.playwright-mcp/eligibilite-original-hero.png` - Site eligibilite.com original

**IMPORTANT** : Regarder ces captures AVANT de coder pour respecter le design existant !

---

## STRUCTURE FINALE DU PROJET

```
multi-sites/eligibilite-clone/
├── index.html              # Landing page (hero, avantages, temoignages, FAQ)
├── formulaire.html         # Formulaire multi-etapes plein ecran
├── merci.html              # Page de confirmation post-soumission
├── PROMPT-V3-COMPLET.md    # Ce fichier (documentation)
└── images/                 # Images existantes
    ├── hero-couple.jpg
    ├── step1-selection.jpg
    ├── step2-eligibility.jpg
    ├── step3-artisan.jpg
    ├── card-pac.jpg
    ├── card-isolation.jpg
    ├── card-solaire.jpg
    ├── famille-reference.jpg
    └── famille-jardin.jpg
```

---

## PLAN D'EXECUTION MULTI-AGENT (5 AGENTS EN PARALLELE)

### AGENT 1 : Formulaire (formulaire.html) - PRIORITE HAUTE

**Fichier** : `multi-sites/eligibilite-clone/formulaire.html`

**Mission** : Creer la page formulaire multi-etapes optimisee pour la conversion

**Specifications detaillees** :

#### Structure HTML
```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Verifiez votre eligibilite aux aides - Simulation gratuite</title>
    <meta name="description" content="Formulaire de verification d'eligibilite aux aides renovation energetique. Resultat en 2 minutes.">
    <!-- Fonts, icons -->
</head>
<body>
    <!-- Header ultra-simplifie -->
    <header class="form-header-minimal">
        <a href="index.html" class="logo">ELIGIBILITE</a>
        <a href="tel:0123456789" class="phone-link">
            <i class="fas fa-phone"></i> Besoin d'aide ? 01 23 45 67 89
        </a>
    </header>

    <!-- Formulaire plein ecran -->
    <main class="form-fullscreen">
        <!-- Progress bar avec etapes -->
        <!-- Conteneur des etapes -->
        <!-- Sidebar avec estimation (desktop) -->
    </main>

    <!-- Pas de footer (focus total) -->
</body>
</html>
```

#### Les 5 Etapes du Formulaire

**ETAPE 1 - Projet** (la plus importante, premiere impression)
- Question : "Quel type de travaux souhaitez-vous realiser ?"
- Options avec icones (cards cliquables) :
  - Pompe a chaleur (icone fa-fan)
  - Isolation (icone fa-home)
  - Panneaux solaires (icone fa-solar-panel)
  - Chaudiere gaz (icone fa-fire)
  - VMC (icone fa-wind)
  - Fenetres/Portes (icone fa-door-open)
  - Plusieurs travaux (icone fa-layer-group)
- Selection multiple possible
- Bouton "Continuer" (pas "Suivant")

**ETAPE 2 - Logement**
- Question : "Parlez-nous de votre logement"
- Champs :
  - Type de bien : Maison / Appartement (2 boutons)
  - Statut : Proprietaire / Locataire (2 boutons)
  - Annee de construction : Select avec plages (Avant 1975, 1975-1990, 1991-2005, 2006-2012, Apres 2012)
  - Surface habitable : Input number avec suffix "m2" (placeholder: "Ex: 120")
- Validation : Surface obligatoire, min 20, max 500

**ETAPE 3 - Chauffage**
- Question : "Votre systeme de chauffage actuel"
- Champs :
  - Type de chauffage actuel : Electrique / Gaz / Fioul / Bois / Autre (5 boutons avec icones)
  - Facture energetique annuelle : Select avec plages (Moins de 1000€, 1000€-1500€, 1500€-2000€, 2000€-2500€, Plus de 2500€)
- Afficher : "Plus votre facture est elevee, plus vous economiserez !"

**ETAPE 4 - Revenus** (etape sensible, rassurer)
- Message de reassurance en haut : "Ces informations nous permettent de calculer precisement vos aides. Elles restent confidentielles."
- Question : "Votre situation fiscale"
- Champs :
  - Nombre de personnes dans le foyer : Select 1-6+
  - Revenu fiscal de reference : Select avec plages par nombre de personnes
    - 1 personne : <16k€, 16-21k€, 21-30k€, >30k€
    - 2 personnes : <24k€, 24-31k€, 31-43k€, >43k€
    - etc.
- Afficher : Estimation des aides mise a jour en temps reel

**ETAPE 5 - Contact** (derniere etape, maximiser completion)
- Message : "Derniere etape ! Ou pouvons-nous vous envoyer votre estimation ?"
- Champs :
  - Civilite : M. / Mme (2 boutons)
  - Prenom : Input text (required)
  - Nom : Input text (required)
  - Email : Input email (required, validation)
  - Telephone : Input tel (OPTIONNEL - marquer clairement)
  - Code postal : Input text 5 chiffres (required, validation)
- Checkboxes :
  - RGPD (obligatoire) : "J'accepte que mes donnees soient traitees pour etre recontacte"
  - Marketing (optionnel) : "J'accepte de recevoir des offres partenaires"
- Bouton final : "DECOUVRIR MES AIDES DISPONIBLES" (orange, gros, anime)

#### Fonctionnalites Formulaire

1. **Progress Bar Animee**
   - 5 cercles numerotes relies par une ligne
   - Cercle actif : bordure orange, scale 1.1
   - Cercles completes : fond orange, coche blanche
   - Barre de progression qui se remplit (0%, 25%, 50%, 75%, 100%)
   - Labels sous chaque cercle : Projet, Logement, Chauffage, Revenus, Contact

2. **Estimation Dynamique des Aides**
   - Panneau lateral (desktop) ou bandeau (mobile)
   - Se met a jour a chaque etape
   - Affiche :
     - MaPrimeRenov' : X XXX €
     - Prime CEE : X XXX €
     - Eco-PTZ : Jusqu'a 50 000 €
     - TVA reduite : 5,5%
     - **TOTAL : XX XXX €**
   - Animation de compteur quand les montants changent

3. **Validation Temps Reel**
   - Bordure verte + coche quand champ valide
   - Bordure rouge + message d'erreur quand invalide
   - Validation APRES que l'utilisateur quitte le champ (pas pendant la saisie)

4. **Transitions Entre Etapes**
   - Slide horizontal (gauche vers droite)
   - Duration: 400ms, easing: cubic-bezier(0.4, 0, 0.2, 1)
   - Fade in des nouveaux elements

5. **Sauvegarde LocalStorage**
   - Sauvegarder les reponses a chaque etape
   - Proposer de reprendre si l'utilisateur revient
   - Expiration apres 24h

6. **Animation de Soumission**
   - Bouton devient loader spinner
   - Message "Calcul de vos aides en cours..."
   - Redirect vers merci.html apres 2 secondes

#### Elements de Conversion

- Badge "Gratuit et sans engagement" visible en permanence
- Badge "Donnees securisees" avec icone cadenas
- Micro-temoignage rotatif en sidebar : "Marie, 54 ans - 8 400€ d'aides obtenues"
- Indicateur "Plus que X etapes" qui diminue
- Timer discret "Temps moyen : 2 min"

#### Mobile (375px+)
- Formulaire plein ecran (pas de scroll horizontal)
- Un champ visible a la fois (ou groupe logique)
- Boutons 56px de hauteur minimum
- Clavier numerique pour telephone et code postal
- Sticky button "Continuer" en bas
- Progress bar simplifiee (juste barre + pourcentage)

**Criteres de succes Agent 1** :
- [ ] 5 etapes fonctionnelles avec navigation
- [ ] Validation de tous les champs
- [ ] Estimation dynamique qui se met a jour
- [ ] Responsive parfait mobile/desktop
- [ ] Sauvegarde localStorage
- [ ] Redirection vers merci.html
- [ ] < 100KB de code HTML total

---

### AGENT 2 : Page Merci (merci.html)

**Fichier** : `multi-sites/eligibilite-clone/merci.html`

**Mission** : Creer la page de confirmation post-soumission

**Specifications detaillees** :

#### Structure
```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <title>Felicitations ! Votre demande a ete envoyee - Eligibilite</title>
</head>
<body>
    <header class="header-simple">
        <!-- Logo seulement -->
    </header>

    <main class="success-page">
        <!-- Animation de succes -->
        <section class="success-hero">
            <!-- Checkmark anime + confetti -->
            <!-- Titre + sous-titre -->
        </section>

        <!-- Recapitulatif -->
        <section class="recap">
            <!-- Resume des reponses du formulaire -->
        </section>

        <!-- Prochaines etapes -->
        <section class="next-steps">
            <!-- Timeline des 3 prochaines etapes -->
        </section>

        <!-- Cross-sell -->
        <section class="cross-sell">
            <!-- Autres services -->
        </section>
    </main>

    <footer class="footer-simple">
        <!-- Liens legaux -->
    </footer>
</body>
</html>
```

#### Contenu Detaille

1. **Animation de Succes** (hero)
   - Grand cercle vert avec checkmark anime (dessine stroke)
   - Confetti qui tombent (15-20 particules, couleurs variees)
   - Titre : "Felicitations !"
   - Sous-titre : "Votre demande d'estimation a ete envoyee avec succes"
   - Badge : "Un conseiller vous contactera sous 24h"

2. **Recapitulatif de la Demande**
   - Card avec fond gris clair
   - Afficher (depuis localStorage) :
     - Type de projet : [valeur]
     - Surface : [valeur] m2
     - Code postal : [valeur]
     - Estimation des aides : [montant total] €
   - Lien "Modifier ma demande" → retour formulaire

3. **Prochaines Etapes** (timeline verticale)
   - Etape 1 (active) : "Un conseiller analyse votre dossier" - Icone loupe
   - Etape 2 : "Appel telephonique sous 24h" - Icone telephone
   - Etape 3 : "Visite technique gratuite" - Icone maison
   - Etape 4 : "Devis personnalise" - Icone document

4. **Cross-Sell**
   - Titre : "Decouvrez aussi nos autres aides"
   - 3 cards horizontales :
     - PAC : "Jusqu'a 11 000€ d'aides"
     - Isolation : "Jusqu'a 75€/m2"
     - Solaire : "Jusqu'a 2 340€ de prime"
   - Chaque card → lien vers formulaire avec pre-selection

5. **Footer**
   - Bouton "Retour a l'accueil" → index.html
   - Liens : Mentions legales, Politique de confidentialite
   - Copyright

#### Fonctionnalites

- Lire les donnees depuis localStorage
- Si pas de donnees, afficher message generique
- Nettoyer localStorage apres affichage (optionnel)
- Animation d'entree : elements apparaissent en cascade (stagger 100ms)

**Criteres de succes Agent 2** :
- [ ] Animation checkmark + confetti
- [ ] Recapitulatif depuis localStorage
- [ ] Timeline prochaines etapes
- [ ] Cross-sell avec liens
- [ ] Responsive mobile
- [ ] < 50KB de code HTML

---

### AGENT 3 : Landing Page (index.html)

**Fichier** : `multi-sites/eligibilite-clone/index.html`

**Mission** : Modifier la landing page existante (enlever formulaire, ajouter liens, ameliorer)

**Specifications detaillees** :

#### Sections a GARDER et AMELIORER

1. **Header**
   - Logo + Navigation
   - Bouton CTA → `href="formulaire.html"`
   - Menu mobile hamburger
   - Dark mode au scroll (deja fait)

2. **Hero Section**
   - Titre avec typewriter effect (garder)
   - Sous-titre
   - Bouton CTA orange → `href="formulaire.html"`
   - Image hero avec trust badge
   - Compteur avis anime (garder)
   - AJOUTER : Bandeau urgence anime en haut "Aides en baisse en 2026 - Profitez-en maintenant !"

3. **Section "Comment ca marche"** (3 etapes)
   - Garder les 3 cards avec images
   - Ameliorer animations hover

4. **Section "Quels travaux"** (grille de cards)
   - Garder la grille
   - Chaque card → `href="formulaire.html?type=pac"` (avec parametre)

5. **NOUVELLE Section "Pourquoi nous choisir"**
   - 4 cards avec icones :
     - "100% gratuit" - icone euro barre
     - "Sans engagement" - icone check
     - "Artisans RGE certifies" - icone badge
     - "Accompagnement complet" - icone hands

6. **Section Temoignages**
   - Garder les temoignages existants
   - AJOUTER : Note moyenne + nombre d'avis
   - AJOUTER : Logos partenaires/certifications

7. **Section FAQ**
   - Garder l'accordeon
   - AJOUTER : 2-3 questions supplementaires sur les aides

8. **Footer**
   - Garder structure
   - AJOUTER : Liens mentions legales, politique confidentialite

#### Sections a SUPPRIMER

- Toute la section `.form-section` (le formulaire)
- Le CSS du formulaire (environ 500 lignes)
- Le JS du formulaire (environ 300 lignes)

#### Modifications des CTA

Tous les boutons doivent pointer vers `formulaire.html` :
```html
<a href="formulaire.html" class="btn-orange">
    Verifier mon eligibilite <i class="fas fa-arrow-right"></i>
</a>
```

Liste des boutons a modifier :
- Bouton header "Verifiez votre eligibilite"
- Bouton hero "SIMULEZ MES ECONOMIES D'ENERGIE"
- Boutons dans les cards travaux
- Bouton dans la section FAQ
- Sticky CTA mobile

#### Nouveaux Elements a Ajouter

1. **Bandeau Urgence** (tout en haut, avant le header)
```html
<div class="urgency-banner">
    <p><strong>ATTENTION :</strong> Aides en baisse en 2026 -
    <a href="formulaire.html">Verifiez votre eligibilite maintenant</a></p>
</div>
```
CSS : fond orange, texte blanc, animation pulse subtile

2. **Compteur de demandes** (dans le hero ou sous le hero)
```html
<div class="social-proof-counter">
    <span class="counter">247</span> demandes aujourd'hui
</div>
```
JS : Incrementer aleatoirement toutes les 30s

3. **Section "Ils nous font confiance"**
```html
<section class="trust-section">
    <div class="trust-logos">
        <!-- Logos : MaPrimeRenov, RGE, QualiPAC, Qualibat -->
    </div>
</section>
```

**Criteres de succes Agent 3** :
- [ ] Formulaire supprime
- [ ] Tous les CTA pointent vers formulaire.html
- [ ] Bandeau urgence ajoute
- [ ] Section "Pourquoi nous" ajoutee
- [ ] Compteur social proof ajoute
- [ ] Code allegece (< 150KB)
- [ ] Pas de JS mort

---

### AGENT 4 : Verification & Tests

**Mission** : Verifier que tout fonctionne correctement

**Taches** :

1. **Verifier les liens entre pages**
   - [ ] index.html → formulaire.html (tous les CTA)
   - [ ] formulaire.html → merci.html (apres soumission)
   - [ ] merci.html → index.html (retour accueil)
   - [ ] merci.html → formulaire.html (cross-sell)

2. **Tester le formulaire**
   - [ ] Etape 1 : Selection projet fonctionne
   - [ ] Etape 2 : Validation champs fonctionne
   - [ ] Etape 3 : Selection chauffage fonctionne
   - [ ] Etape 4 : Calcul aides fonctionne
   - [ ] Etape 5 : Validation contact fonctionne
   - [ ] Navigation precedent/suivant
   - [ ] Progress bar se met a jour
   - [ ] Estimation se met a jour
   - [ ] Soumission redirige vers merci.html

3. **Tester le responsive**
   - [ ] index.html sur mobile (375px)
   - [ ] formulaire.html sur mobile (375px)
   - [ ] merci.html sur mobile (375px)
   - [ ] Pas de scroll horizontal
   - [ ] Boutons assez grands (48px+)

4. **Verifier les performances**
   - [ ] index.html < 150KB
   - [ ] formulaire.html < 100KB
   - [ ] merci.html < 50KB
   - [ ] Pas d'erreurs console JS
   - [ ] Pas d'erreurs CSS

5. **Creer un rapport**
   - Ecrire les resultats dans `multi-sites/eligibilite-clone/TESTS-REPORT.md`

**Criteres de succes Agent 4** :
- [ ] Rapport de tests complet
- [ ] Tous les liens fonctionnent
- [ ] Formulaire complet fonctionne
- [ ] Responsive OK
- [ ] Performance OK

---

### AGENT 5 : Deploiement & Dashboard

**Mission** : Deployer et mettre a jour le dashboard principal

**Taches** :

1. **Mettre a jour le dashboard** (`index.html` a la racine)
   - Modifier la carte "Eligibilite Clone" pour refleter V3
   - Ajouter mention "Multi-pages" dans la description
   - Verifier que le lien pointe vers `/multi-sites/eligibilite-clone/`

2. **Mettre a jour CLAUDE.md**
   - Ajouter les nouvelles pages dans la table des pages actives
   - Documenter la structure multi-pages

3. **Git commit**
```bash
git add .
git commit -m "Eligibilite Clone V3: Restructuration multi-pages

- index.html: Landing page optimisee (sans formulaire)
- formulaire.html: Formulaire 5 etapes plein ecran
- merci.html: Page de confirmation avec recap

Ameliorations:
- Meilleure UX formulaire
- Estimation aides en temps reel
- Animations de succes
- Mobile-first responsive
- Performance optimisee

Generated with Claude Code"
```

4. **Deployer sur Vercel**
```bash
git push
npx vercel --prod --yes
```

5. **Verifier le deploiement**
   - Ouvrir https://solar-forms-hub.vercel.app/multi-sites/eligibilite-clone/
   - Tester le parcours complet
   - Verifier que tout fonctionne en production

**Criteres de succes Agent 5** :
- [ ] Dashboard mis a jour
- [ ] CLAUDE.md mis a jour
- [ ] Commit cree
- [ ] Push effectue
- [ ] Deploiement Vercel reussi
- [ ] Site live fonctionne

---

### AGENT 6 : Generation d'Images IA (OPTIONNEL - Parallele avec 1,2,3)

**Mission** : Generer des images professionnelles avec Fal.ai pour ameliorer le site

**MCP requis** : `mcp__fal-ai__run_model`

**IMPORTANT** : Ne PAS utiliser `mcp__fal-ai__generate_image` (bug connu)

**Methode** :
```javascript
// Utiliser run_model
mcp__fal-ai__run_model({
    model_id: "fal-ai/flux/dev",
    input: {
        prompt: "...",
        num_images: 1,
        image_size: "landscape_16_9"
    }
})

// Puis telecharger l'image
Bash: curl -o "multi-sites/eligibilite-clone/images/nom.jpg" "URL_RETOURNEE"
```

**Images a generer** :

| Nom fichier | Prompt | Utilisation |
|-------------|--------|-------------|
| `hero-famille-moderne.jpg` | "Happy French middle-aged couple standing in front of their modern renovated house with solar panels on roof, sunny day, garden, professional real estate photography, warm colors" | Hero landing page |
| `success-thumbsup.jpg` | "Professional French man giving thumbs up, smiling, modern office background, business casual, trustworthy, bright lighting" | Page merci |
| `artisan-installation.jpg` | "French certified technician in blue uniform installing heat pump unit outside house, professional work, safety equipment, sunny day" | Section etapes |
| `maison-renovee.jpg` | "Beautiful French house after complete energy renovation, new insulation, modern windows, solar panels, before/after comparison style, professional architecture photography" | Cards travaux |
| `famille-economie.jpg` | "Happy French family looking at reduced energy bill, kitchen table, modern interior, surprised and happy expressions, natural lighting" | Temoignages |
| `conseiller-telephone.jpg` | "Professional French energy consultant on phone call, modern office, computer screen showing energy charts, friendly smile, business attire" | Prochaines etapes |

**Tailles recommandees** :
- Hero : `landscape_16_9` (1920x1080)
- Cards : `landscape_4_3` (800x600)
- Portraits : `portrait_3_4` (600x800)

**Workflow** :
1. Generer l'image avec Fal.ai
2. Recuperer l'URL retournee
3. Telecharger avec curl dans le bon dossier
4. Verifier que l'image est bien la
5. Passer a l'image suivante

**Criteres de succes Agent 6** :
- [ ] 6 images generees
- [ ] Images telechargees dans images/
- [ ] Qualite professionnelle
- [ ] Coherence visuelle entre les images
- [ ] Pas de texte/artefacts dans les images

---

## PALETTE DE COULEURS (OBLIGATOIRE)

```css
:root {
    /* Couleurs principales */
    --blue-dark: #1E3A8A;
    --blue-primary: #2563EB;
    --blue-light: #3B82F6;

    /* Orange (CTA) */
    --orange: #F97316;
    --orange-light: #FB923C;
    --orange-dark: #EA580C;

    /* Texte */
    --text-dark: #1F2937;
    --text-gray: #6B7280;

    /* Backgrounds */
    --gray-light: #F3F4F6;
    --gray-border: #E5E7EB;
    --white: #FFFFFF;

    /* Succes/Erreur */
    --green: #10B981;
    --red: #EF4444;
}
```

---

## FONTS & ICONS (OBLIGATOIRE)

```html
<!-- Google Fonts -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&display=swap" rel="stylesheet">

<!-- Font Awesome -->
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

<!-- AOS Animations -->
<link href="https://unpkg.com/aos@2.3.1/dist/aos.css" rel="stylesheet">
<script src="https://unpkg.com/aos@2.3.1/dist/aos.js"></script>
```

---

## ANIMATIONS REQUISES

### Formulaire
```css
/* Transition entre etapes */
.step-transition {
    animation: slideIn 0.4s cubic-bezier(0.4, 0, 0.2, 1);
}

@keyframes slideIn {
    from { opacity: 0; transform: translateX(30px); }
    to { opacity: 1; transform: translateX(0); }
}

/* Validation succes */
.input-valid {
    border-color: var(--green);
    animation: validPulse 0.3s ease;
}

@keyframes validPulse {
    0%, 100% { box-shadow: 0 0 0 0 rgba(16, 185, 129, 0.4); }
    50% { box-shadow: 0 0 0 4px rgba(16, 185, 129, 0.2); }
}

/* Bouton CTA pulse */
.btn-cta {
    animation: ctaPulse 2s ease-in-out infinite;
}

@keyframes ctaPulse {
    0%, 100% { box-shadow: 0 0 0 0 rgba(249, 115, 22, 0.4); }
    50% { box-shadow: 0 0 20px 5px rgba(249, 115, 22, 0.2); }
}
```

### Page Merci
```css
/* Checkmark anime */
.checkmark {
    stroke-dasharray: 166;
    stroke-dashoffset: 166;
    animation: checkmark 0.6s ease forwards;
}

@keyframes checkmark {
    to { stroke-dashoffset: 0; }
}

/* Confetti */
.confetti {
    animation: confetti-fall 3s ease-out forwards;
}

@keyframes confetti-fall {
    0% { transform: translateY(-100vh) rotate(0deg); opacity: 1; }
    100% { transform: translateY(100vh) rotate(720deg); opacity: 0; }
}
```

---

## REGLES TECHNIQUES STRICTES

1. **HTML/CSS/JS vanilla uniquement** - Pas de React, Vue, etc.
2. **Tout dans un seul fichier HTML par page** - CSS et JS inline
3. **Mobile-first** - Concevoir d'abord pour 375px puis adapter desktop
4. **Performance** - Chaque fichier < 150KB
5. **Accessibilite** - Labels sur tous les inputs, contraste suffisant
6. **SEO** - Meta title et description uniques par page
7. **RGPD** - Case obligatoire pour le consentement

---

## COMMENT LANCER CE PROMPT

### Dans une NOUVELLE session Claude Code :

**COMMANDE COMPLETE (recommandee)** :
```
Lis le fichier multi-sites/eligibilite-clone/PROMPT-V3-COMPLET.md

Regarde les captures d'ecran de reference :
- .playwright-mcp/.playwright-mcp/eligibilite-v2-desktop-hero.png
- .playwright-mcp/.playwright-mcp/eligibilite-v2-formulaire-desktop.png
- .playwright-mcp/.playwright-mcp/eligibilite-v2-mobile-hero.png

Execute le plan avec 6 agents :

PHASE 1 - EN PARALLELE (4 agents simultanement) :
- Agent 1 : Cree formulaire.html (pas besoin de MCP)
- Agent 2 : Cree merci.html (pas besoin de MCP)
- Agent 3 : Modifie index.html (pas besoin de MCP)
- Agent 6 : Genere les images IA avec mcp__fal-ai__run_model

PHASE 2 - VERIFICATION (apres phase 1) :
- Agent 4 : Teste tout avec mcp__playwright (screenshots, navigation)

PHASE 3 - DEPLOIEMENT (apres phase 2) :
- Agent 5 : Deploy avec mcp__vercel et mcp__github

Chaque agent utilise SEULEMENT les MCP dont il a besoin pour economiser le contexte.
```

### Commande simplifiee :

```
Execute multi-sites/eligibilite-clone/PROMPT-V3-COMPLET.md avec 6 agents.
Phase 1 parallele : Agents 1,2,3,6 (code + images).
Phase 2 : Agent 4 (tests Playwright).
Phase 3 : Agent 5 (deploy Vercel).
```

### Commande ultra-courte :

```
PROMPT-V3-COMPLET.md dans eligibilite-clone. 6 agents, parallele, tests, deploy.
```

---

## CHECKLIST FINALE

### Pages
- [ ] `formulaire.html` cree et fonctionnel
- [ ] `merci.html` cree et fonctionnel
- [ ] `index.html` modifie (sans formulaire)

### Liens
- [ ] index → formulaire (tous les CTA)
- [ ] formulaire → merci (soumission)
- [ ] merci → index (retour)
- [ ] merci → formulaire (cross-sell)

### Fonctionnalites
- [ ] Formulaire 5 etapes complet
- [ ] Validation temps reel
- [ ] Estimation aides dynamique
- [ ] Sauvegarde localStorage
- [ ] Animation succes avec confetti
- [ ] Recapitulatif sur page merci

### Responsive
- [ ] Mobile 375px OK
- [ ] Tablet 768px OK
- [ ] Desktop 1200px OK

### Performance
- [ ] index.html < 150KB
- [ ] formulaire.html < 100KB
- [ ] merci.html < 50KB

### Images IA (Agent 6)
- [ ] hero-famille-moderne.jpg generee
- [ ] success-thumbsup.jpg generee
- [ ] artisan-installation.jpg generee
- [ ] maison-renovee.jpg generee
- [ ] famille-economie.jpg generee
- [ ] conseiller-telephone.jpg generee
- [ ] Images integrees dans les pages HTML

### Tests (Agent 4)
- [ ] TESTS-REPORT.md cree
- [ ] Screenshots Playwright pris
- [ ] Tous les liens testes
- [ ] Formulaire complet teste
- [ ] Mobile teste

### Deploiement (Agent 5)
- [ ] Dashboard index.html mis a jour
- [ ] CLAUDE.md mis a jour
- [ ] Git commit
- [ ] Git push
- [ ] Vercel deploy
- [ ] Site live fonctionne
- [ ] URL finale testee

---

## NOTES IMPORTANTES

1. **Regarder les captures AVANT de coder** pour respecter le design
2. **Tester sur mobile en priorite** (68% du trafic)
3. **Ne pas sur-ingenierer** - garder le code simple et lisible
4. **Commenter le code** aux endroits complexes
5. **Verifier les liens** entre toutes les pages avant de deployer

---

Cree par Claude Code - Session du 02/12/2025
