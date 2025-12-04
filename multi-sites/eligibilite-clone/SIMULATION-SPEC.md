# Specs Simulation Formulaire - Eligibilite Clone

## Objectif Principal
Transformer le formulaire en une **simulation exceptionnelle** qui donne envie de remplir jusqu'au bout et d'être rappelé.

---

## Philosophie UX

### Le mantra
> "Donner des informations, mais créer l'envie d'en savoir PLUS"

### Principes clés
1. **Jamais ennuyeux** - Chaque étape doit engager
2. **Interactif** - Cliquer = avancer (pas de bouton "Suivant" classique)
3. **Valeur perçue** - L'utilisateur doit sentir qu'il obtient quelque chose
4. **Mystère calculé** - Donner assez pour intéresser, pas assez pour satisfaire
5. **Mobile-first** - 80% du trafic est mobile

---

## Structure du Flow (3 Phases)

### PHASE A - Engagement (Questions faciles)
**Objectif** : Faire entrer l'utilisateur dans le flow sans friction

Questions typiques :
- Type de logement (maison/appartement)
- Propriétaire ou locataire
- Année de construction
- Surface habitable
- Code postal
- Nombre de personnes dans le foyer
- Type de chauffage actuel

**UX** :
- Choix visuels (icônes cliquables)
- Progression visible
- Pas de champs texte libre (que des clics)

---

### PHASE B - Sélection Activités (Le coeur)
**Objectif** : Qualifier le lead sur les produits rentables

Activités principales (MUST HAVE au moins 1) :
- Panneaux solaires
- Pompe à chaleur
- Isolation (murs extérieurs)

Activités secondaires (bonus) :
- Fenêtres / menuiseries
- Isolation combles
- Ballon thermodynamique

**UX** :
- Sélection multiple possible
- Mettre en avant les AIDES disponibles pour chaque activité
- Afficher les économies potentielles
- Animations au survol/sélection

**Psychologie** :
- Les gens ADORENT les aides (MaPrimeRénov, Anah, CEE, TVA réduite)
- Montrer les montants possibles les motive
- Ne pas fermer les choix (fait peur) mais orienter

---

### PHASE C - Informations Personnelles (La friction)
**Objectif** : Récupérer les coordonnées malgré la résistance naturelle

Champs requis :
- Prénom
- Nom
- Email
- Téléphone

**UX CRUCIALE** :
- Animations maximales ici
- Justifier pourquoi on demande (ex: "Pour recevoir votre estimation personnalisée")
- Montrer ce qu'ils vont obtenir
- Barre de progression proche de la fin (95%)
- Effet "presque terminé"

---

### PAGE FINALE - Résultat + Remerciements
**Objectif** : Donner de la valeur mais garder le mystère

Afficher :
- Estimation des aides (fourchette, pas chiffre exact)
- Produits sélectionnés
- "Un conseiller va vous rappeler pour affiner"
- Peut-être : autres produits complémentaires

**Ne PAS afficher** :
- Chiffre trop précis (pas crédible)
- Tout le détail (sinon plus besoin du rappel)

---

## Animations & Micro-interactions

### Obligatoires
- Transition fluide entre étapes (slide ou fade)
- Feedback visuel au clic (ripple, scale, couleur)
- Barre de progression animée
- "Calcul en cours..." avec spinner avant résultat final

### Recommandées
- Icônes qui s'animent au hover
- Confettis ou célébration à la fin
- Chiffres qui s'incrémentent (compteur animé)
- Parallax léger sur mobile

### À éviter
- Animations trop longues (max 300ms)
- Trop de mouvements simultanés
- Animations qui bloquent l'interaction

---

## Données & Calculs

### Sources de données
- Fichier DONNEES-2025.md (barèmes officiels)
- MaPrimeRénov : selon revenus et zone
- CEE : selon travaux
- Anah : selon profil

### Logique de calcul
- Doit être CREDIBLE (pas de chiffres exagérés)
- Afficher une FOURCHETTE (ex: "Entre 8 000€ et 12 000€")
- Baser sur les vrais barèmes 2025
- Adapter selon les réponses (surface, revenus, zone)

---

## Contraintes Techniques

- HTML/CSS/JS vanilla (pas de framework)
- Mobile-first (base 375px)
- Touch targets minimum 48px
- Performance : < 100KB total
- Animations CSS (pas JS si possible)
- Fonctionne sans JavaScript (progressive enhancement)

---

## Métriques de Succès

1. **Taux de complétion** : % qui finissent le formulaire
2. **Drop-off par étape** : Identifier où les gens abandonnent
3. **Qualité des leads** : Au moins 1 produit principal sélectionné
4. **Mobile UX** : Pas de zoom, pas de scroll horizontal

---

## Références & Inspirations

À rechercher :
- Typeform (animations entre questions)
- Simulateurs gouvernementaux (crédibilité)
- Leadgen immo/energie (conversion)

---

## Notes Business

- **Objectif final** : Lead rappelé par commercial
- **Produits prioritaires** : PAC, Isolation, Solaire
- **Cible** : Propriétaires de maison en France
- **Motivation principale des users** : Les AIDES financières

---

*Dernière mise à jour : 04/12/2025*
