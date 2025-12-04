# COPIE CE PROMPT DANS UNE NOUVELLE CONVERSATION

```
## CONTEXTE - Projet Éligibilité V4

### État actuel
- **Formulaire V3** : Terminé et fonctionnel (multi-sélection aides, transitions lentes, messages encourageants)
- **Pages existantes** :
  - `index.html` : Page d'accueil (à refaire)
  - `maprimerenov.html` : Guide MaPrimeRénov'
  - `prime-cee.html` : Guide Prime CEE
  - `anah.html` : Guide Anah
  - `pompe-a-chaleur.html` : Page travaux PAC
  - `isolation.html` : Page travaux isolation
  - `panneaux-solaires.html` : Page travaux solaire
  - `formulaire.html` : Formulaire V3 (OK)
  - `merci.html` : Page de remerciement

### Problèmes actuels des pages
1. Design daté, pas assez "premium"
2. Pas assez de CTAs pour convertir
3. Les aides ne sont pas mises en avant visuellement
4. Manque d'interactivité (chaque clic devrait être récompensé)
5. Pas de cohérence visuelle entre les pages
6. Pas optimisé conversion seniors (40-50+ ans)

## OBJECTIF V4 - Refonte complète des pages

### Vision
Créer un site ultra-focalisé sur les **AIDES** avec :
- Design moderne, premium, rassurant
- CTAs partout (sticky, inline, after-scroll)
- Interactivité maximale (animations au scroll, hover effects, micro-interactions)
- Focus sur les montants d'aides (gros chiffres, couleurs vives)
- Confiance (labels officiels, témoignages, garanties)

### Pages à refaire (par priorité)
1. **index.html** - Page d'accueil (conversion principale)
2. **maprimerenov.html** - Guide aide #1
3. **prime-cee.html** - Guide aide #2
4. Pages travaux (PAC, isolation, solaire)

### Design System V4
- **Couleurs** : Bleu profond (#1E3A8A), Orange CTA (#F97316), Vert succès (#10B981)
- **Typo** : Inter (déjà en place)
- **Boutons** : 60px min-height, border-radius 16px, ombres prononcées
- **Cards** : Fond blanc, border-radius 24px, hover lift effect
- **Animations** : AOS scroll reveal, hover scale, micro-interactions

## APPROCHE BMAD (Build Measure Analyze Deploy)

### Agents à utiliser
1. **Agent Architect** : Planifier la structure des pages
2. **Agent Designer** : Créer le design system et les composants
3. **Agent Developer** : Implémenter les pages
4. **Agent QA** : Tester sur mobile 375px avec Playwright

### Workflow
1. Architect planifie → valide avec user
2. Designer crée composants réutilisables
3. Developer implémente page par page
4. QA teste et capture screenshots

## RESSOURCES DISPONIBLES

### Images (dossier images/)
- hero-couple.jpg, famille-reference.jpg, famille-jardin.jpg
- hero-pac.jpg, hero-isolation.jpg, hero-solaire.jpg
- card-pac.jpg, card-isolation.jpg, card-solaire.jpg
- icon-mpr.jpg, icon-cee.jpg, icon-anah.jpg
- artisan-heatpump.jpg, rge-certified-artisan.jpg
- energy-bill-savings.jpg, thermography-house.jpg
- modern-eco-house.jpg, french-house-garden.jpg
- senior-couple-solar.jpg, family-warm-living.jpg
- facade-before-after.jpg, roof-solar-comparison.jpg
- heatpump-diagram.jpg, technician-roof-solar.jpg
- maprimerenov-document.jpg, energy-advisor.jpg
- cozy-winter-interior.jpg

### Données aides 2025
- MPR Bleu : PAC 5000€, Isolation 75€/m²
- MPR Jaune : PAC 4000€, Isolation 60€/m²
- MPR Violet : PAC 3000€, Isolation 40€/m²
- CEE Zone H1 : PAC 4500€, Isolation 12€/m²
- CEE Zone H2 : PAC 3800€, Isolation 10€/m²
- Aides régionales : 800€ à 2000€ selon département

### MCP disponibles
- **Playwright** : Tests mobile 375px, screenshots
- **Perplexity** : Recherche infos actualisées
- **Vercel** : Déploiement
- **Fal.ai** : Génération images si besoin

## CONTRAINTES TECHNIQUES

- HTML/CSS/JS vanilla (un fichier par page)
- Mobile-first 375px
- < 100KB par page
- Touch targets 48px minimum
- Support prefers-reduced-motion
- Fonts : Inter (Google Fonts)
- Icons : Font Awesome 6

## LIVRABLES ATTENDUS

### Phase 1 : Architecture (validation user)
- [ ] Plan détaillé de chaque page
- [ ] Wireframes textuels des sections
- [ ] Liste des composants réutilisables

### Phase 2 : Développement
- [ ] Design system CSS (variables, composants)
- [ ] index.html refait
- [ ] maprimerenov.html refait
- [ ] prime-cee.html refait
- [ ] Pages travaux refaites

### Phase 3 : QA
- [ ] Screenshots Playwright de chaque page
- [ ] Tests conversion (CTAs cliquables)
- [ ] Vérification accessibilité

## INSTRUCTIONS POUR L'AGENT

1. **Commence par lire** ce fichier et les pages existantes
2. **Propose un plan** détaillé pour la page index.html
3. **Attends validation** avant de coder
4. **Utilise la méthode BMAD** : plusieurs agents en parallèle si possible
5. **Documente** chaque décision dans docs/

GO !
```
