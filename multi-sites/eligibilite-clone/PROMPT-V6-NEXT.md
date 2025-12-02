# PROMPT V6 - PROCHAINES ÉTAPES
**Date :** 02/12/2025
**Statut :** Planification
**Projet :** Eligibilite-clone - Site complet génération leads rénovation énergétique

---

## 📊 État actuel V5 (Complété)

### ✅ Réalisations V5
- **9 pages HTML complètes** avec navigation fonctionnelle
- **30 images IA** générées et intégrées (36 fichiers au total, 6 non utilisés supprimés)
- **Maillage interne** optimal (165 liens entre pages)
- **Navigation dropdown** fonctionnelle (dispositifs + aides)
- **Responsive** 375px+ validé
- **Performance** : pages < 100KB chacune
- **SEO** : meta descriptions, alt texts, structure H1-H6

### 📄 Pages actives
1. **index.html** - Landing principale (83KB)
2. **formulaire.html** - Formulaire 5 étapes (63KB)
3. **merci.html** - Confirmation (33KB)
4. **panneaux-solaires.html** - Page dispositif (41KB)
5. **isolation.html** - Page dispositif (41KB)
6. **pompe-a-chaleur.html** - Page dispositif (42KB)
7. **maprimerenov.html** - Page aide (35KB)
8. **prime-cee.html** - Page aide (34KB)
9. **anah.html** - Page aide (39KB)

### 🖼️ Images utilisées (30)
**Heroes (6):**
- hero-couple.jpg, hero-solaire.jpg, hero-isolation.jpg, hero-pac.jpg

**Cards dispositifs (3):**
- card-solaire.jpg, card-isolation.jpg, card-pac.jpg

**Icons aides (3):**
- icon-mpr.jpg, icon-cee.jpg, icon-anah.jpg

**Steps (3):**
- step1-selection.jpg, step2-eligibility.jpg, step3-artisan.jpg

**Familles (3):**
- famille-reference.jpg, famille-jardin.jpg, family-warm-living.jpg

**Réassurance (8):**
- french-house-garden.jpg, rge-certified-artisan.jpg, senior-couple-solar.jpg, energy-advisor.jpg

**Techniques (4):**
- technician-roof-solar.jpg, roof-solar-comparison.jpg, facade-before-after.jpg, thermography-house.jpg, heatpump-diagram.jpg

**Démonstrations (3):**
- maprimerenov-document.jpg, energy-bill-savings.jpg, cozy-winter-interior.jpg, modern-eco-house.jpg, artisan-heatpump.jpg

---

## 🎯 Objectifs V6 - Optimisation Conversion

### 1. Tests A/B et Analytics (PRIORITÉ 1)

#### Intégration tracking
```html
<!-- Google Analytics 4 -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXX"></script>

<!-- Hotjar -->
<script>
    (function(h,o,t,j,a,r){
        // Code Hotjar
    })(window,document,'https://static.hotjar.com/c/hotjar-','.js?sv=');
</script>

<!-- Meta Pixel -->
<script>
  !function(f,b,e,v,n,t,s)
  // Code Meta
</script>
```

#### Événements à tracker
- **Formulaire :**
  - Début formulaire
  - Chaque étape complétée (1-5)
  - Abandon (quelle étape ?)
  - Soumission finale
- **Navigation :**
  - Clics CTA "Je teste mon éligibilité"
  - Clics menu dropdown
  - Scroll depth (25%, 50%, 75%, 100%)
  - Temps passé sur page
- **Engagement :**
  - Clics téléphone
  - Clics images
  - Ouverture FAQ

#### KPIs à mesurer
- Taux de conversion formulaire : **objectif 3-5%**
- Taux de complétion formulaire : **objectif >60%**
- Taux de rebond : **objectif <50%**
- Temps moyen sur site : **objectif >2min**
- Pages par session : **objectif >2.5**

---

### 2. Amélioration Formulaire (PRIORITÉ 2)

#### Optimisations UX
- **Sauvegarde automatique** : localStorage amélioré avec notification "Vos données sont sauvegardées"
- **Validation en temps réel** : feedback visuel immédiat sur chaque champ
- **Indicateur de progression** : "Étape 2/5 - Plus que 3 minutes"
- **Boutons "Retour"** : permettre de modifier les réponses précédentes facilement
- **Préremplissage intelligent** : détecter code postal → région, suggérer surface moyenne

#### Tests A/B formulaire
**Test 1 : Longueur du formulaire**
- Variant A : 5 étapes (actuel)
- Variant B : 3 étapes (regroupe logement+chauffage)
- Variant C : 7 étapes (plus granulaire)

**Test 2 : CTA final**
- Variant A : "DÉCOUVRIR MES AIDES DISPONIBLES" (actuel)
- Variant B : "CALCULER MES AIDES EN 30 SEC"
- Variant C : "RECEVOIR MON ESTIMATION GRATUITE"

**Test 3 : Panel estimation**
- Variant A : Visible dès le début (actuel)
- Variant B : Apparaît seulement à l'étape 3
- Variant C : Animation progressive des montants

---

### 3. Enrichissement Contenu (PRIORITÉ 3)

#### Nouvelles sections à ajouter

**Section "Témoignages vidéo"**
```html
<section class="video-testimonials">
    <h2>Ils ont sauté le pas</h2>
    <div class="video-grid">
        <!-- 3-4 vidéos courtes (30-60 sec) -->
        <!-- Miniatures avec bouton play -->
    </div>
</section>
```

**Section "Garanties"**
- Artisans RGE certifiés
- Assurance décennale
- Garantie satisfaction 30 jours
- SAV réactif 7j/7

**Section "Processus en détail"**
- Timeline visuelle du A à Z
- Photos avant/après
- Durée estimée par étape

**Blog/Actualités**
- "Nouveautés aides 2025"
- "Retour d'expérience client du mois"
- "Conseils rénovation énergétique"

#### Calculateurs interactifs
**Calculateur économies**
- Input : facture actuelle
- Output : projection économies sur 10/20 ans
- Graphique visuel

**Calculateur ROI**
- Coût total travaux
- Aides déduites
- Économies annuelles
- Retour sur investissement (années)

---

### 4. SEO et Référencement (PRIORITÉ 3)

#### Pages manquantes
- **sitemap.xml** : génération automatique
- **robots.txt** : optimisation crawl
- **404.html** : page d'erreur custom
- **Blog** : articles SEO (5-10 articles minimum)

#### Optimisations techniques
- **Schema.org** : LocalBusiness, FAQPage, BreadcrumbList
- **Open Graph** : partage réseaux sociaux
- **Canonical URLs** : éviter duplicate content
- **Lazy loading** : images below the fold
- **Minification** : CSS/JS (actuellement inline)

#### Contenu SEO
**Mots-clés longue traîne à cibler :**
- "combien coûte une pompe à chaleur avec aides 2025"
- "isolation combles perdus prix au m2 avec MPR"
- "panneaux solaires autoconsommation rentabilité"
- "éligibilité MaPrimeRénov revenus modestes"

**Articles blog à créer :**
1. "Guide complet MaPrimeRénov' 2025 : tout ce qui change"
2. "Pompe à chaleur vs chaudière gaz : que choisir ?"
3. "Isolation : par où commencer pour maximiser les économies ?"
4. "Panneaux solaires : 5 erreurs à éviter absolument"
5. "CEE : comment cumuler toutes les aides en 2025 ?"

---

### 5. Landing Pages Spécifiques (PRIORITÉ 4)

#### Par région
- landing-ile-de-france.html
- landing-auvergne-rhone-alpes.html
- landing-provence.html
- etc.

**Contenu régionalisé :**
- Nombre d'installations dans la région
- Artisans locaux partenaires
- Spécificités climatiques
- Aides locales complémentaires

#### Par type de lead
- landing-pac-urgent.html (fioul → PAC)
- landing-solaire-rentabilite.html (investissement)
- landing-isolation-confort.html (problème froid)

**Contenu ciblé :**
- Headline ultra-personnalisé
- Problème spécifique adressé
- Témoignage pertinent
- Urgence adaptée

---

### 6. Tunnel de Nurturing (PRIORITÉ 4)

#### Email séquence post-formulaire
**J0 - Confirmation immédiate**
- Récap des informations
- Estimation provisoire
- Prochaines étapes
- Vidéo explicative

**J+1 - Ressources utiles**
- Guide PDF "Tout savoir sur [dispositif choisi]"
- Comparatif aides disponibles
- FAQ détaillée

**J+3 - Relance douce**
- "Avez-vous des questions ?"
- Proposition RDV téléphonique
- Témoignage client similaire

**J+7 - Urgence**
- Rappel diminution aides 2026
- Places artisans limitées
- Offre spéciale du moment

**J+14 - Dernière chance**
- Dernier rappel
- Lien réactivation dossier

#### SMS (optionnel)
- J+0 : Confirmation réception
- J+2 : Rappel RDV conseiller
- J+7 : Urgence baisse aides

---

### 7. Optimisations Performance (PRIORITÉ 5)

#### Vitesse de chargement
- **Critical CSS** : inline pour ATF
- **Defer JS** : charger scripts après DOM
- **WebP images** : conversion .jpg → .webp (-30% poids)
- **CDN** : hébergement images externe (Cloudinary, Cloudflare)

#### Audit Lighthouse
**Objectifs :**
- Performance : >90
- Accessibility : 100
- Best Practices : 100
- SEO : 100

#### Progressive Web App (PWA)
- Manifest.json
- Service Worker
- Installation sur mobile
- Fonctionnement offline (formulaire)

---

### 8. Intégrations Techniques (PRIORITÉ 5)

#### CRM
- **HubSpot / Salesforce** : synchronisation leads
- Scoring automatique (chaud/tiède/froid)
- Segmentation par type de projet

#### Automatisation
- **Zapier / Make** : workflows automatiques
  - Formulaire → CRM + Email + SMS
  - Qualification lead → Assignation commercial
  - RDV pris → Notification équipe

#### Téléphonie
- **CallTrackingMetrics** : numéro dynamique par source
- Enregistrement appels
- Retranscription automatique
- Analytics appels

---

## 📈 Roadmap Priorités

### Phase 1 (Urgent - Q1 2025)
1. ✅ Intégration Google Analytics + Hotjar
2. ✅ Tests A/B formulaire (3 variants)
3. ✅ Optimisation SEO technique

### Phase 2 (Important - Q2 2025)
4. Création 10 articles blog SEO
5. Landing pages régionales (5 régions prioritaires)
6. Calculateurs interactifs (économies + ROI)

### Phase 3 (Souhaitable - Q3 2025)
7. Vidéos témoignages (5 clients)
8. Email nurturing automatisé
9. PWA + optimisation performance avancée

### Phase 4 (Nice-to-have - Q4 2025)
10. Intégrations CRM avancées
11. Chatbot IA
12. Landing pages ultra-ciblées (20+)

---

## 💰 Budget Estimé V6

### Développement
- Tests A/B + Analytics : **3-5 jours dev**
- Optimisations formulaire : **2-3 jours dev**
- Landing pages régionales : **1 jour / page**
- Blog + CMS : **3-5 jours dev**
- Calculateurs : **2-3 jours / calculateur**
- PWA : **3-5 jours dev**

### Contenu
- Rédaction articles blog : **300-500€ / article** (x10)
- Vidéos témoignages : **500-1000€ / vidéo** (x5)
- Photos professionnelles : **1000-2000€** (shooting)

### Outils SaaS (mensuel)
- Google Analytics : **Gratuit**
- Hotjar : **39€/mois** (Business)
- Mailchimp/Sendinblue : **49€/mois**
- CallTracking : **99€/mois**
- CRM (HubSpot) : **45€/mois** (Starter)

**Total estimé Phase 1-2 : 5 000 - 8 000 €**

---

## 🎨 Design Évolutions

### V6 UI/UX
- **Dark mode** : option toggle header
- **Micro-animations** : boutons, transitions
- **Illustrations custom** : remplacer certaines photos stock
- **Icônes animées** : SVG + Lottie
- **Gradients modernes** : tendances 2025

### Accessibilité
- Contraste WCAG AAA
- Navigation clavier complète
- Screen reader friendly
- Sous-titres vidéos

---

## 🔐 Conformité & Légal

### RGPD
- Politique de confidentialité détaillée
- Gestion consentements granulaire
- Droit à l'oubli (suppression données)
- Export données utilisateur

### CGU/CGV
- Conditions d'utilisation
- Mentions légales complètes
- Politique cookies
- Charte qualité

---

## 📊 Métriques de Succès V6

### Objectifs 6 mois
- **+50% de leads qualifiés** vs V5
- **Taux de conversion** : 3-5% (vs 1-2% moyenne)
- **Coût par lead** : <50€
- **NPS (Net Promoter Score)** : >40

### Objectifs 12 mois
- **+150% de leads qualifiés** vs V5
- **Taux de conversion** : 5-8%
- **Coût par lead** : <30€
- **Top 3 Google** sur 10 requêtes clés

---

## 🤝 Partenariats & Croissance

### Affiliés
- Influenceurs éco-responsabilité
- Comparateurs énergie
- Blogs immobilier/déco

### Co-marketing
- Partenaires artisans RGE
- Fournisseurs matériaux
- Collectivités locales

---

## 📝 Notes Techniques

### Stack actuel
- HTML/CSS/JS vanilla
- AOS (animations)
- Font Awesome (icons)
- Google Fonts (Inter)

### Stack recommandé V6
- **Ajout :** Tailwind CSS (styling)
- **Ajout :** Alpine.js (interactivité légère)
- **Ajout :** Vite (bundler)
- **Conservation :** Vanilla JS (pas de framework lourd)

---

## ✅ Quick Wins Immédiats

1. **Ajout n° de téléphone** visible header (sticky)
2. **Widget WhatsApp** en bas à droite
3. **Badge Trustpilot** dynamique (API)
4. **Pop-up exit intent** : "Ne partez pas ! -10% sur devis"
5. **Chat support** : Tawk.to gratuit
6. **Comparateur avant/après** slider interactif
7. **Section presse** : "Vu dans : TF1, BFM, Le Figaro"
8. **Compteur temps réel** : "X personnes en ligne"

---

**Document créé par Agent 6 (Chef de Projet) - V5 Review**
**Prochaine révision :** Janvier 2025
**Contact :** [À compléter]
