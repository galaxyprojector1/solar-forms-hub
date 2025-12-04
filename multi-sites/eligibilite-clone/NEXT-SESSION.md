# SESSION SUIVANTE - Amélioration Formulaire V2

## ÉTAPE 1 : INSTALLER BMAD (à faire toi-même)

```bash
cd C:\Users\yohann\Desktop\solar-forms-hub\solar-forms-hub
npx bmad-method@alpha install
```

Cela installe le système multi-agents complet avec party-mode.

---

## ÉTAPE 2 : PROMPT POUR LA NOUVELLE CONVERSATION

Copie-colle ce bloc dans une nouvelle conversation Claude Code :

```
## CONTEXTE PROJET

Je travaille sur un formulaire de simulation d'aides à la rénovation énergétique.
- URL : https://solar-forms-hub.vercel.app/multi-sites/eligibilite-clone/formulaire.html
- Code : C:\Users\yohann\Desktop\solar-forms-hub\solar-forms-hub\multi-sites\eligibilite-clone\formulaire.html

## VERSION ACTUELLE (V1)

Le formulaire V1 fonctionne avec :
- 6 écrans (logement → propriétaire → code postal → surface → travaux → contact)
- Clic = avance automatique (pas de bouton "Suivant")
- Aides affichées sur chaque travaux (PAC: 11k€, Isolation: 8k€, etc.)
- Counter total animé en temps réel
- Écran de calcul avec spinner + confettis à la fin

## PROBLÈMES IDENTIFIÉS (Screenshots disponibles)

Sur mobile 375px, les écrans 1 à 4 ont BEAUCOUP D'ESPACE VIDE en bas.
La card blanche est en haut, le fond bleu en bas est vide.
Screenshots dans : C:\Users\yohann\Desktop\solar-forms-hub\.playwright-mcp\formulaire-mobile-screen*.png

## AMÉLIORATIONS V2 DEMANDÉES (par priorité)

### P0 - Centrage vertical mobile
Les écrans 1-4 doivent centrer le contenu verticalement dans la card.
Actuellement : card en haut, espace bleu vide en bas.

### P1 - Loader après code postal
Après saisie du code postal valide :
1. Afficher loader "Recherche des aides dans votre région..."
2. Pause 1.5-2 secondes
3. Message "X aides disponibles dans le [Département]"
4. Puis continuer vers écran surface

### P2 - Pré-cocher les travaux populaires
Sur l'écran travaux, pré-cocher automatiquement :
- Pompe à chaleur (11 000€)
- Isolation thermique (8 000€)
Total affiché dès l'arrivée : 19 000€
L'utilisateur peut décocher s'il veut.

### P3 - Afficher infos sur les aides
Avant/après le code postal, afficher :
- Zone climatique (H1/H2/H3) basée sur le département
- Liste des aides : MaPrimeRénov', CEE, aides régionales

## FICHIERS À LIRE

1. `multi-sites/eligibilite-clone/formulaire.html` - Code actuel
2. `multi-sites/eligibilite-clone/docs/4-next-iteration.md` - Specs détaillées
3. `multi-sites/eligibilite-clone/SIMULATION-SPEC.md` - Specs originales

## OUTILS DISPONIBLES (MCP)

- **Playwright** : pour tester le rendu mobile (375px)
- **Vercel** : pour déployer
- **GitHub** : pour commit/push

## CE QUE JE VEUX

1. Utilise le système BMAD si installé (.bmad/) avec *workflow-init
2. Sinon, fais les 4 améliorations P0-P3 directement
3. Teste avec Playwright sur mobile 375px
4. Déploie sur Vercel
5. Montre-moi les screenshots avant/après

GO !
```

---

## SCREENSHOTS DISPONIBLES (Mobile 375px)

| Fichier | Contenu | Problème |
|---------|---------|----------|
| formulaire-mobile-screen1.png | Écran type logement | ESPACE VIDE en bas |
| formulaire-mobile-screen2.png | Écran propriétaire | ESPACE VIDE en bas |
| formulaire-mobile-screen3-codepostal.png | Code postal vide | ESPACE VIDE en bas |
| formulaire-mobile-screen3-filled.png | Code postal rempli | ESPACE VIDE en bas |
| formulaire-mobile-screen4-surface.png | Slider surface | ESPACE VIDE en bas |
| formulaire-mobile-screen5-travaux.png | Sélection travaux | OK - utilise bien l'espace |
| formulaire-mobile-screen5-selected.png | Travaux sélectionnés | OK |
| formulaire-mobile-screen6-contact.png | Formulaire contact | OK |

---

## RÉSUMÉ DES AMÉLIORATIONS

```
AVANT (V1)                          APRÈS (V2)
─────────────────────────────────────────────────────
Card en haut, vide en bas     →    Contenu centré verticalement
Code postal → Surface direct  →    Code postal → Loader régional → Surface
Travaux vides au départ       →    PAC + Isolation pré-cochés (19k€)
Pas d'infos sur les aides     →    Zone H1/H2/H3 + liste des aides
```
