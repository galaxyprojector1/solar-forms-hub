# TODO - Prochaines Améliorations Formulaires Solaires

## FAIT (Session 1er décembre 2025)

- [x] Créer structure dossiers (formulaires/, landing-pages/, versions-completes/)
- [x] Déplacer v1 à v10 dans `/versions-completes/`
- [x] Hub mis à jour avec catégories
- [x] V11 - Clean Conversion
- [x] V12 - Trust Builder
- [x] V13 - Urgency
- [x] V14 - Mobile Ultra

---

## PROCHAINES TÂCHES

### CIBLE : Propriétaires de maison en France

---

### 1. LANDING PAGES COMPLÈTES (dossier `/landing-pages/`)

Chaque landing page = Hero + Argumentaire + Formulaire intégré + Footer

- [ ] **lp-panneaux-solaires** - Landing dédiée panneaux solaires PV
- [ ] **lp-pompe-a-chaleur** - Landing dédiée PAC (pompe à chaleur)
- [ ] **lp-isolation-exterieure** - Landing dédiée ITE (isolation thermique extérieure)
- [ ] **lp-multi-travaux** - Landing avec les 3 activités (solaire + PAC + isolation)
- [ ] **lp-simulateur-aides** - Simulateur d'aides financières (MaPrimeRénov, CEE, etc.)

> Quand on clique sur "Landing Pages" dans le hub, ça affiche la page de présentation avec toutes les landing pages (comme pour les formulaires)

---

### 2. NOUVEAUX FORMULAIRES (dossier `/formulaires/`)

Formulaires spécialisés par activité :

- [ ] **f-panneaux-solaires** - Formulaire spécialisé solaire
- [ ] **f-pompe-a-chaleur** - Formulaire spécialisé PAC
- [ ] **f-isolation** - Formulaire spécialisé isolation
- [ ] **f-multi-travaux** - Formulaire multi-activités (choix du type de travaux)
- [ ] **f-simulateur-aides** - Simulateur aides financières (revenus, situation, etc.)

> Quand on clique sur "Formulaires" dans le hub, ça affiche la page de présentation avec tous les formulaires

---

### 3. METTRE À JOUR LE HUB

- [ ] Page de présentation pour `/landing-pages/` (comme index.html principal)
- [ ] Page de présentation pour `/formulaires/`
- [ ] Les liens du hub principal pointent vers ces pages de présentation

---

## STRUCTURE CIBLE

```
solar-forms-hub/
├── index.html                    ← Hub principal
│
├── formulaires/
│   ├── index.html                ← Page présentation formulaires
│   ├── f-panneaux-solaires/
│   ├── f-pompe-a-chaleur/
│   ├── f-isolation/
│   ├── f-multi-travaux/
│   └── f-simulateur-aides/
│
├── landing-pages/
│   ├── index.html                ← Page présentation landing pages
│   ├── lp-panneaux-solaires/
│   ├── lp-pompe-a-chaleur/
│   ├── lp-isolation-exterieure/
│   ├── lp-multi-travaux/
│   └── lp-simulateur-aides/
│
└── versions-completes/           ← V1 à V14 (déjà fait)
    └── ...
```

---

## ÉLÉMENTS CLÉS POUR CHAQUE LANDING PAGE

```
✅ Hero accrocheur (titre + sous-titre + CTA)
✅ Avantages / Bénéfices (économies, écologie, confort)
✅ Aides financières mentionnées (MaPrimeRénov, CEE, TVA réduite)
✅ Formulaire intégré
✅ Témoignages / Avis clients
✅ Badges confiance (RGE, garanties)
✅ Footer avec mentions légales
```

---

## CONTRAINTES TECHNIQUES

```
✅ Fichier unique HTML
✅ CDN uniquement
✅ Mobile first
✅ < 200KB
✅ Fonctionne en iframe
✅ Touch-friendly
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

# VÉRIFIER que c'est visible sur Vercel AVANT de dire "terminé"
```

---

*Mis à jour le 1er décembre 2025*
