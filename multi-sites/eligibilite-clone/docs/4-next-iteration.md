# Prochaine Itération - Améliorations Formulaire V2

## Améliorations Demandées

### 1. Écran de chargement après Code Postal
**Objectif** : Créer de l'anticipation + vérifier les aides régionales
- Après saisie du code postal (5 chiffres valides)
- Afficher un loader "Recherche des aides dans votre région..."
- Durée : 1.5-2 secondes
- Afficher ensuite un message "X aides régionales disponibles !"

### 2. Pré-cocher les travaux populaires
**Objectif** : Réduire la friction, augmenter l'engagement
- Sur l'écran travaux, pré-cocher PAC + Isolation (les plus demandés)
- L'utilisateur peut décocher s'il ne veut pas
- Le compteur démarre déjà à 19 000€

### 3. Améliorer l'utilisation de l'espace mobile
**Constat Playwright** : Écrans 1-4 ont beaucoup d'espace vide en bas
**Solutions possibles** :
- Centrer verticalement le contenu dans la card
- Ajouter des éléments de réassurance en bas (badges, témoignages)
- Agrandir les éléments interactifs
- Card qui prend plus de hauteur (min-height: 70vh?)

### 4. Ajouter des informations sur les aides
**Objectif** : Donner envie de continuer avant la sélection travaux
- Après le code postal, afficher un résumé :
  - "Dans votre département : MaPrimeRénov', Prime CEE, Aides régionales"
  - Badge "Zone H1/H2/H3" selon le code postal
- Sur chaque travaux, info-bulle avec détails

## Screenshots Playwright (375px)
- `formulaire-mobile-screen1.png` : Écran type logement - ESPACE VIDE
- `formulaire-mobile-screen2.png` : Écran propriétaire - ESPACE VIDE
- `formulaire-mobile-screen3-codepostal.png` : Code postal - ESPACE VIDE
- `formulaire-mobile-screen4-surface.png` : Surface - ESPACE VIDE
- `formulaire-mobile-screen5-travaux.png` : Travaux - BON
- `formulaire-mobile-screen6-contact.png` : Contact - BON

## Données Techniques Nécessaires

### Zones climatiques par département
```javascript
const zonesClimatiques = {
  H1: ['01','02','03',...], // Nord, Est, Massif Central
  H2: ['14','22','29',...], // Ouest, Sud-Ouest
  H3: ['06','13','83',...], // Méditerranée
};
```

### Aides régionales (exemples)
- Île-de-France : Éco-rénovons Paris, MaPrimeRénov' Copro
- Occitanie : Éco-chèque logement
- AURA : Prime Région

## Priorité des Changements
1. **P0** : Centrage vertical / utilisation espace mobile
2. **P1** : Loader après code postal + message régional
3. **P2** : Pré-cochage travaux populaires
4. **P3** : Infos détaillées sur les aides
