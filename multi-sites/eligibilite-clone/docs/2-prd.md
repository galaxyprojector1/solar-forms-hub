# Phase 2 - PRD Nouveau Formulaire

## Objectif
Formulaire de simulation avec taux de complétion > 60%, clic = avancer.

## Flow en 3 Phases

### PHASE A - Engagement (4 questions, ~30 sec)
1. **Type logement** → Maison / Appartement (2 cards cliquables)
2. **Propriétaire?** → Oui / Non (auto-avance)
3. **Code postal** → Input 5 chiffres + validation zone
4. **Surface** → Slider visuel 50-250m²

**UX** : Chaque clic = animation + avance automatique

### PHASE B - Sélection Travaux (1 écran, ~20 sec)
**Cards interactives avec aides affichées :**
- PAC : "Jusqu'à 11 000€ d'aides"
- Isolation : "Jusqu'à 75€/m²"
- Solaire : "Jusqu'à 4 000€ de prime"

**Multi-sélection** : Check animé, total aides mis à jour en temps réel
**Sélection min** : 1 produit principal requis

### PHASE C - Contact (1 écran, ~40 sec)
- Barre progression à 90%
- Message "Dernière étape pour recevoir votre estimation"
- Champs : Prénom, Nom, Email, Téléphone
- Justification : "Pour vous envoyer votre estimation personnalisée"

## Animations Obligatoires
1. Transition slide entre questions (300ms)
2. Ripple effect au clic
3. Counter animé des aides
4. "Calcul en cours..." (2-3 sec) avec spinner
5. Confettis à la soumission

## Données Techniques
- Barèmes 2025 de DONNEES-2025.md
- Fourchette d'aides (pas de chiffre exact)
- Calcul selon : zone, revenus estimés, travaux

## Critères de Succès
- Temps complétion < 2 min
- Mobile : aucun scroll horizontal, aucun zoom
- Touch targets : 48px minimum
- Poids total : < 80KB

## Hors Scope
- Intégration API backend
- Système de paiement
- Dashboard admin
