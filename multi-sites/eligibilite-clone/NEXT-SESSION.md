# Prochaine Session - Eligibilite Clone

## ÉTAT ACTUEL (04/12/2024)
- `index.html` : Refonte mobile V5 FAITE, CTA visible sans scroll
- Bandeau urgence orange : SUPPRIMÉ
- Compteur "347 simulations" : SUPPRIMÉ (hero + sticky CTA)

## À FAIRE (priorité)

### 1. Supprimer formulaire contact bas de page (index.html ~ligne 2443)
```html
<!-- Dans section faq-section, supprimer le <form class="contact-form"> -->
<!-- Garder uniquement la FAQ -->
```

### 2. Fixer compteurs animés (~ligne 2340)
Les compteurs `data-target` affichent 0. Mettre valeurs fixes :
- 8 252 installations financées
- 44 195 foyers conseillés

### 3. Vérifier liens → conversion
Tous clics → `formulaire.html` ou pages produits

## FICHIERS À SUPPRIMER
```bash
rm BMAD-CONTEXT.md NEXT-SESSION-V4.md SIMULATION-SPEC.md
rm docs/NEXT-SESSION-V4.md docs/4-next-iteration.md
```

## FICHIERS UTILES
- `docs/BMAD-SPECS.md` - Design system
- `docs/ASSETS-DATA.md` - Images

## DEPLOY
```bash
git add . && git commit -m "fix" && git push && npx vercel --prod --yes
```

## URL
https://solar-forms-hub.vercel.app/multi-sites/eligibilite-clone/
