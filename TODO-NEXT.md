# TODO - Prochaines Améliorations Formulaires Solaires

## FAIT (Session 1er décembre 2025)

- [x] Structure dossiers créée
- [x] V1 à V10 déplacées dans `/versions-completes/`
- [x] V11 Clean, V12 Trust, V13 Urgency, V14 Mobile créées
- [x] Hub principal mis à jour

---

## PROCHAINES TÂCHES

### CIBLE : Propriétaires de maison en France
### OBJECTIF : MAXIMUM DE LEADS / CONVERSION (exagération autorisée !)

---

### 1. LANDING PAGES COMPLÈTES (dossier `/landing-pages/`)

Chaque landing page = Page complète ultra-persuasive

**À CRÉER :**
- [ ] **lp-panneaux-solaires** - Landing complète panneaux solaires PV
- [ ] **lp-pompe-a-chaleur** - Landing complète PAC
- [ ] **lp-isolation-exterieure** - Landing complète ITE
- [ ] **lp-multi-travaux** - Landing avec les 3 activités au choix
- [ ] **lp-simulateur-aides** - Simulateur MaPrimeRénov / CEE / aides

- [ ] **`/landing-pages/index.html`** - Page de présentation de toutes les landing pages

**UTILISER PERPLEXITY POUR :**
- Rechercher les meilleurs sites concurrents (Effy, HelloWatt, Sonergia, etc.)
- S'inspirer de leurs arguments de vente
- Trouver les chiffres clés (économies, aides, etc.)
- Copier les meilleures pratiques de conversion

---

### 2. FORMULAIRES (dossier `/formulaires/`)

**À CRÉER :**
- [ ] **f-panneaux-solaires** - Formulaire spécialisé solaire
- [ ] **f-pompe-a-chaleur** - Formulaire spécialisé PAC
- [ ] **f-isolation** - Formulaire spécialisé isolation
- [ ] **f-multi-travaux** - Formulaire multi-activités
- [ ] **f-simulateur-aides** - Simulateur aides (revenus, situation)

- [ ] **`/formulaires/index.html`** - Page de présentation de tous les formulaires

---

### 3. METTRE À JOUR LE HUB PRINCIPAL

- [ ] Lien "Landing Pages" → `/landing-pages/index.html`
- [ ] Lien "Formulaires" → `/formulaires/index.html`

---

## ÉLÉMENTS CLÉS LANDING PAGE (EXAGÉRATION MAX)

```
✅ Hero CHOC (chiffres impressionnants, urgence)
✅ Compteur économies animé DÈS LE DÉBUT
✅ "Jusqu'à 70% d'économies" / "Jusqu'à 90% financé par l'État"
✅ Aides : MaPrimeRénov, CEE, TVA 5.5%, Éco-PTZ
✅ Témoignages clients (avec photos, villes)
✅ Badges : RGE, Garantie 10-25 ans, 15000+ clients
✅ Urgence : "Offre limitée", "X places restantes"
✅ FOMO : "32 personnes regardent cette page"
✅ Formulaire intégré avec progression visible
✅ Footer confiance (mentions, certifications)
```

---

## STRUCTURE CIBLE

```
solar-forms-hub/
├── index.html                    ← Hub principal
│
├── formulaires/
│   ├── index.html                ← PAGE PRÉSENTATION FORMULAIRES
│   ├── f-panneaux-solaires/
│   ├── f-pompe-a-chaleur/
│   ├── f-isolation/
│   ├── f-multi-travaux/
│   └── f-simulateur-aides/
│
├── landing-pages/
│   ├── index.html                ← PAGE PRÉSENTATION LANDING PAGES
│   ├── lp-panneaux-solaires/
│   ├── lp-pompe-a-chaleur/
│   ├── lp-isolation-exterieure/
│   ├── lp-multi-travaux/
│   └── lp-simulateur-aides/
│
└── versions-completes/           ← V1 à V14 (FAIT)
```

---

## RECHERCHE PERPLEXITY À FAIRE

Avant de créer chaque landing page, rechercher :

```
1. "meilleur site devis panneaux solaires France"
2. "landing page pompe à chaleur conversion"
3. "simulateur aides rénovation énergétique"
4. "arguments vente isolation extérieure"
5. "chiffres économies PAC France 2024"
6. "MaPrimeRénov montants 2024 2025"
```

S'inspirer de : Effy, HelloWatt, Sonergia, Engie, TotalEnergies, QuelleEnergie

---

## CONTRAINTES TECHNIQUES

```
✅ Fichier unique HTML
✅ CDN uniquement
✅ Mobile first
✅ < 200KB
✅ Touch-friendly
✅ EXAGÉRATION pour conversion max
✅ Cible : propriétaires maison France
```

---

## RÈGLE POUR L'AGENT

```bash
# TOUJOURS après modification :
git add .
git commit -m "description"
git push
vercel --prod --yes

# VÉRIFIER sur Vercel AVANT de dire "terminé" !
```

---

*Mis à jour le 1er décembre 2025*
