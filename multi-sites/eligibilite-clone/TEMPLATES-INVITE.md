# INVITE TEMPLATES - Simulation Formulaire Exceptionnelle

## Instructions pour Claude (nouvelle session)

### CONTEXTE
Tu vas utiliser un **agent orchestrateur autonome** avec les templates de `claude-code-templates` pour transformer le formulaire de simulation.

**Fichier de specs (LIS-LE EN PREMIER) :**
- `SIMULATION-SPEC.md` - Toutes les specs UX/business

**Fichier à transformer :**
- `formulaire.html`

---

### TA MISSION (AUTONOME)

Tu es l'orchestrateur. Fais TOUT en autonomie :

1. Lis `SIMULATION-SPEC.md`
2. Analyse `formulaire.html`
3. Conçois le nouveau flow
4. Implémente les changements
5. Teste sur mobile (viewport 375px)
6. Commit + Push
7. Déploie sur Vercel

**RETOURNE UNIQUEMENT :**
- URL de production
- 3 bullet points des changements majeurs

---

### RÈGLES CRITIQUES (OPTIMISATION CONTEXTE)

1. **NE DEMANDE RIEN**
   - Tu as toutes les specs dans SIMULATION-SPEC.md
   - Décide toi-même

2. **PAS DE RAPPORT DÉTAILLÉ**
   - Pas de "voici ce que j'ai fait étape par étape"
   - Juste le résultat final

3. **TOUT EN UNE PASSE**
   - Pas de va-et-vient
   - Tu fais, tu déploies, tu retournes l'URL

---

### SPECS BUSINESS (RÉSUMÉ)

**Objectif** : Simulation qui donne envie de remplir jusqu'au bout

**Flow en 3 phases :**
- A) Questions faciles (engagement)
- B) Sélection activités (PAC, Isolation, Solaire) + mise en avant AIDES
- C) Infos personnelles (animations max pour réduire friction)

**UX obligatoire :**
- Mobile-first
- Clic = avancer (pas de bouton "Suivant")
- Animations fluides
- "Calcul en cours..." avant résultat
- Résultat = fourchette crédible

**Voir `SIMULATION-SPEC.md` pour le détail complet.**

---

### CONTRAINTES TECHNIQUES

- HTML/CSS/JS vanilla
- Mobile-first (375px base)
- Touch targets 48px min
- < 100KB total
- Animations CSS (pas JS si possible)

---

### COMMANDE DE DÉPLOIEMENT

```bash
git add . && git commit -m "Simulation v2 - UX exceptionnelle" && git push && npx vercel --prod --yes
```

---

**COMMENCE PAR : Lire SIMULATION-SPEC.md puis agir.**
