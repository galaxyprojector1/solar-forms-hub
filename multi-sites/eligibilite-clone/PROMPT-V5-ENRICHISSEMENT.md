# PROMPT V5 - Site Professionnel et Uniforme

## OBJECTIF

Site **BEAU, FONCTIONNEL et UNIFORME** sur tous les appareils.

**REGLES ABSOLUES :**
- PAS D'EMOJIS (UX professionnelle)
- Belles images de haute qualite
- Header et navigation fonctionnels sur TOUTES les pages
- Design uniforme entre les pages
- Verification visuelle reelle

**URL** : https://solar-forms-hub.vercel.app/multi-sites/eligibilite-clone/

---

## ARCHITECTURE (9 pages)

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
├── images/                 # Images
└── DONNEES-2025.md         # Baremes officiels 2025
```

---

## PLAN MULTI-AGENT (6 Agents)

---

### AGENT 1 : Analyse Sites Concurrents

**MCP** : `mcp__perplexity__perplexity_search`, `mcp__perplexity__perplexity_research`

**Mission** : Analyser les meilleurs sites de renovation energetique pour s'en inspirer.

**Recherches** :
1. "site effy.fr design UX analyse"
2. "site hellio.com landing page"
3. "meilleurs sites renovation energetique France 2024 2025"
4. "landing page lead generation best practices"
5. "animations CSS subtiles professionnelles"

**Output** :
- Liste des sites de reference avec URLs
- Ce qui marche bien (design, UX, animations)
- Ce qu'on peut reprendre
- Palette couleurs recommandee
- Structure de page type

---

### AGENT 2 : Images de Qualite

**MCP** : `mcp__perplexity__perplexity_search`

**Mission** : Trouver ou generer des images de HAUTE QUALITE.

**Option A - Images Stock (PRIORITAIRE)**
Chercher sur Unsplash, Pexels :
- "solar panels house"
- "heat pump installation"
- "home insulation"
- "happy family home"
- "energy efficient house"

**Option B - Generation IA (si necessaire)**
Utiliser `mcp__fal-ai__run_model` avec :
- Modele : `fal-ai/flux/dev`
- Prompts DETAILLES (50+ mots minimum)
- VERIFIER chaque image visuellement avant utilisation

**Output** :
- URLs des images de qualite
- OU images generees et VERIFIEES
- Si une image est mauvaise, ne pas l'utiliser

---

### AGENT 3 : Pilote (Acces Fichiers)

**MCP** : Aucun
**Outils** : Read, Glob, Grep

**Mission** : Lire tous les fichiers et coordonner le travail.

**Taches** :
1. Lire DONNEES-2025.md - extraire montants
2. Analyser chaque page HTML (structure, problemes)
3. Identifier incoherences entre pages
4. Verifier que header/footer sont identiques partout
5. Creer liste des corrections a faire

**Output** :
- Etat de chaque page
- Montants officiels
- Liste des corrections
- Template header/footer uniforme

---

### AGENT 4 : Coordination/Integration

**MCP** : Aucun
**Outils** : Read, Write, Edit

**Mission** : Appliquer les modifications de maniere UNIFORME.

**Regles** :
1. PAS D'EMOJIS
2. Meme header sur TOUTES les pages
3. Meme footer sur TOUTES les pages
4. Meme style CSS
5. Animations subtiles seulement
6. Images bien dimensionnees

**Pour chaque page** :
- Corriger le header si probleme
- Appliquer style uniforme
- Integrer images de l'Agent 2
- Ajouter maillage interne
- CTA vers formulaire

**Output** :
- 9 pages modifiees
- Design uniforme
- Zero emoji

---

### AGENT 5 : QA Visuel

**MCP** : `mcp__playwright__browser_navigate`, `mcp__playwright__browser_snapshot`, `mcp__playwright__browser_take_screenshot`

**Mission** : VERIFIER VISUELLEMENT chaque page.

**Pour CHAQUE page** :
1. Ouvrir avec Playwright
2. Screenshot desktop (1440px)
3. Screenshot mobile (375px)
4. Verifier :
   - Header visible
   - Navigation fonctionne
   - Images OK
   - Pas d'emojis
   - Design coherent

**SI PROBLEME** :
- NE PAS dire OK
- Reporter le probleme
- Retour Agent 4 pour correction

**Output** :
- Screenshots toutes pages
- Rapport OK / Problemes

---

### AGENT 6 : Nettoyage et Deploy

**MCP** : Aucun
**Outils** : Read, Write, Edit, Glob, Bash

**Mission** : Nettoyer et deployer.

**Taches** :
1. Supprimer fichiers inutiles
2. Supprimer images non utilisees
3. Verifier tous les liens
4. Commit + Push + Vercel deploy

```bash
git add .
git commit -m "V5 - Design professionnel uniforme"
git push
npx vercel --prod --yes
```

**Output** :
- Projet propre
- Site deploye
- URL finale

---

## EXECUTION SEQUENTIELLE

Executer les agents UN PAR UN :

```
Agent 1 (Analyse) → verifie output
Agent 2 (Images) → verifie output
Agent 3 (Pilote) → verifie output
Agent 4 (Integration) → verifie output
Agent 5 (QA) → SI OK continue, SINON retour Agent 4
Agent 6 (Deploy)
```

---

## CHECKLIST FINALE

- [ ] Header visible sur 9 pages
- [ ] Navigation fonctionne
- [ ] Zero emoji
- [ ] Belles images
- [ ] Design uniforme
- [ ] Responsive 375px OK
- [ ] Liens fonctionnels
- [ ] Site deploye

---

## COMMANDE

```
Execute les 6 agents EN SEQUENCE.
PAS d'emojis.
Verification visuelle REELLE.
Design PROFESSIONNEL.
```

---

*Qualite > Vitesse*
