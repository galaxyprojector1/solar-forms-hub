# Catalogue des Images - Solar Forms Hub

> Derniere MAJ : 02/12/2025

## Screenshots Playwright (.playwright-mcp/)

Captures d'ecran pour tests et debug. **Ne pas commiter sur git.**

| Fichier | Description |
|---------|-------------|
| `dashboard-multi-sites.png` | Screenshot du dashboard |
| `eligibilite-original-hero.png` | Site original eligibilite.com - Hero |
| `eligibilite-original-aides.png` | Site original eligibilite.com - Section aides |
| `eligibilite-clone-hero.png` | Notre clone - Hero |
| `eligibilite-clone-footer.png` | Notre clone - Footer |
| `eligibilite-clone-full.png` | Notre clone - Page complete |
| `eligibilite-clone-mobile.png` | Notre clone - Version mobile |
| `prime-energie-pro-hero.png` | Prime Energie Pro - Hero |
| `prime-energie-pro-services.png` | Prime Energie Pro - Services |
| `production-prime-energie-pro.png` | Prime Energie Pro en prod |

---

## Images IA Generees

### multi-sites/eligibilite-clone/images/ (9 images)

Clone fidele de eligibilite.com - Generees avec fal-ai/flux/dev

| Fichier | Prompt/Description | Taille |
|---------|-------------------|--------|
| `hero-couple.jpg` | Couple francais souriant devant maison avec panneaux solaires | landscape_16_9 |
| `step1-selection.jpg` | Main touchant tablette avec interface energie | square |
| `step2-eligibility.jpg` | Conseillere service client avec casque | square |
| `step3-artisan.jpg` | Technicien RGE avec tablette devant PAC | square |
| `card-pac.jpg` | Pompe a chaleur installee dehors | portrait_4_3 |
| `card-isolation.jpg` | Salon moderne bien isole | portrait_4_3 |
| `card-solaire.jpg` | Technicien installant panneaux solaires | portrait_4_3 |
| `famille-reference.jpg` | Famille petit-dejeuner cuisine moderne | landscape_4_3 |
| `famille-jardin.jpg` | Mere et fille jardinage | square |

### multi-sites/prime-energie-pro/images/ (25+ images)

Clone ameliore eligibilite.com - Generees avec fal-ai/flux/dev

**Images principales :**
| Fichier | Description |
|---------|-------------|
| `hero-famille.png` | Famille devant maison renovee |
| `couple-facture.png` | Couple regardant facture energie |
| `artisan-rge.png` | Artisan certifie RGE |
| `consultation-expert.png` | Expert en consultation |
| `installation-pac.png` | Installation pompe a chaleur |
| `isolation-murs.png` | Travaux isolation murs |
| `panneaux-solaires-toit.png` | Panneaux solaires sur toit |
| `maison-renovee.png` | Maison apres renovation |
| `logo.png` | Logo Prime Energie Pro |
| `background-pattern.png` | Pattern de fond |

**Icones travaux (images/icons/) :**
| Fichier | Description |
|---------|-------------|
| `pac.png` | Icone pompe a chaleur |
| `isolation.png` | Icone isolation |
| `solaire.png` | Icone panneaux solaires |
| `chaudiere.png` | Icone chaudiere |
| `vmc.png` | Icone VMC |
| `fenetres.png` | Icone fenetres |

**Badges certifications (images/badges/) :**
| Fichier | Description |
|---------|-------------|
| `rge-certifie.png` | Badge RGE |
| `maprimenov.png` | Badge MaPrimeRenov |
| `prime-cee.png` | Badge Prime CEE |
| `eco-ptz.png` | Badge Eco-PTZ |
| `tva-55.png` | Badge TVA 5.5% |

**Temoignages (images/testimonials/) :**
| Fichier | Description |
|---------|-------------|
| `jeune-couple.png` | Photo jeune couple |
| `femme-40.png` | Photo femme 40 ans |
| `homme-senior.png` | Photo homme senior |
| `couple-retraites.png` | Photo couple retraites |

### public/images/prime-reno/ (12 images)

LP Prime Renovation - Generees avec fal-ai/flux/dev

| Fichier | Description |
|---------|-------------|
| `villa-sunset.jpg` | Villa moderne au coucher de soleil |
| `famille-heureuse.jpg` | Famille heureuse dans salon |
| `maison-solaire.jpg` | Maison avec panneaux solaires |
| `pompe-chaleur.jpg` | Pompe a chaleur exterieure |
| `isolation.jpg` | Travaux d'isolation |
| `technicien-rge.jpg` | Technicien certifie |
| `conseiller.jpg` | Conseiller energie |
| `app-economies.jpg` | Application economies |
| `vue-aerienne.jpg` | Vue aerienne maisons |
| `temoignage-couple.jpg` | Photo temoignage couple |
| `temoignage-femme.jpg` | Photo temoignage femme |
| `temoignage-homme.jpg` | Photo temoignage homme |

### public/images/ (images generiques)

| Fichier | Description | Utilise par |
|---------|-------------|-------------|
| `family-solar-hero.jpg` | Famille avec panneaux | LP Solaire V2 |
| `technician-install.jpg` | Technicien installation | LP Solaire V2 |
| `aides-financieres.jpg` | Illustration aides | LP Solaire V2 |
| `savings-solar.png` | Economies solaire | LP Solaire V2 |
| `hero-ecosystem.png` | Ecosysteme energie | Renovation 2025 |
| `heat-pump.png` | Pompe a chaleur | Renovation 2025 |
| `insulation.png` | Isolation | Renovation 2025 |
| `ev-charging.png` | Borne recharge | Renovation 2025 |
| `maprimerenov.png` | Logo MaPrimeRenov | Plusieurs pages |

---

## Regles pour nouvelles images

1. **Generer avec fal-ai** :
```
model_id: "fal-ai/flux/dev"
input: {"prompt": "...", "num_images": 1, "image_size": "landscape_16_9"}
```

2. **Telecharger** :
```bash
curl -o "chemin/nom.jpg" "URL_RETOURNEE"
```

3. **Ajouter a ce fichier** avec description

4. **Tailles recommandees** :
   - Hero : `landscape_16_9` (1024x576)
   - Cartes : `portrait_4_3` (768x1024)
   - Icones : `square` (512x512)
   - Temoignages : `square` (512x512)

5. **Nommage** : minuscules, tirets, descriptif
   - Bon : `famille-jardin.jpg`, `hero-couple.jpg`
   - Mauvais : `IMG_001.jpg`, `image2.png`
