# Maquettes EDUFOODS — mode d'emploi Figma

## 1. Importer les maquettes
Glisse les 14 fichiers `.svg` dans une page Figma. Chaque fichier devient un frame avec des calques modifiables (textes, formes, icônes).
Les polices Poppins et Inter sont déjà disponibles dans Figma.

## 2. Installer le plugin (variables + prototype)
1. Dézippe `Plugin_Figma_EDUFOODS.zip`.
2. Dans l'application **Figma Desktop** : menu **Plugins → Développement → Importer un plugin depuis un manifeste…** et choisis `manifest.json`.
3. Mets les 14 frames sur la même page, sans les renommer (le plugin les reconnaît grâce au numéro 01 à 14 au début du nom).
4. Lance **Plugins → Développement → EDUFOODS – Variables et prototype → Tout faire**.

Le menu du plugin propose aussi « Créer les variables couleur » et « Créer les liens du prototype » séparément.

Le plugin crée la collection de variables **EDUFOODS** et relie chaque remplissage et contour à sa variable.
Ensuite, change une couleur dans le panneau **Variables locales** : toutes les maquettes suivent.

Si tu importes de nouveaux SVG plus tard, relance simplement le plugin : il supprime ses anciens liens avant d'en créer de nouveaux, sans doublons.

## 2 bis. Le prototype
Le plugin ajoute 32 zones cliquables invisibles (calques nommés « ↪ … ») et 5 parcours de démarrage :
- **Parcours étudiant (mobile)** : Accueil → Restaurant → Panier groupé → Paiement → Suivi, plus le Profil par la barre d'onglets.
- **Parcours chauffeur** : Livraisons disponibles → Accepter → Livraison en cours → Confirmer.
- **Espace restaurant** : Tableau de bord ⇄ Menu et offres de gros.
- **Back-office** : Tableau de bord ⇄ Gestion des restaurants.
- **Site vitrine** : page qui défile, boutons vers l'app, l'espace restaurant et l'espace chauffeur.

Pour le tester, va dans l'onglet **Prototype**, choisis un parcours et clique sur ▶ (Présenter). Dans les réglages du prototype, choisis un appareil (par exemple iPhone 14 pour le mobile).
La carte `00_Carte_du_prototype.png` montre toutes les zones cliquables et leur destination.

## 3. Palette (12 variables)
| Variable | Hex | Usage |
|---|---|---|
| Marque/Principal | #2BB673 | Boutons, éléments actifs |
| Marque/Principal foncé | #1E8E57 | Textes sur fond clair, prix |
| Marque/Principal clair | #E3F6EC | Fonds de cartes, badges |
| Marque/Accent | #FF8A3D | Réductions, commandes groupées |
| Marque/Accent clair | #FFEEDF | Fonds de bannières |
| Neutres/Texte | #1E2A38 | Titres et textes |
| Neutres/Texte secondaire | #6B7785 | Descriptions |
| Neutres/Bordure | #E4E8E6 | Contours, séparateurs |
| Neutres/Fond | #F7F9F6 | Fond des écrans |
| Neutres/Surface | #FFFFFF | Cartes, barres |
| États/Alerte | #E5484D | Erreurs, priorité haute |
| États/Alerte clair | #FDE8E8 | Fond des alertes |

`EDUFOODS_couleurs.tokens.json` contient la même palette au format design tokens (importable avec le plugin Tokens Studio si tu préfères).

## 4. Plan de secours sans plugin
Sélectionne tous les frames. Dans le panneau de droite, rubrique **Couleurs de la sélection**, chaque couleur de la palette apparaît une seule fois : clique sur l'icône de variable à côté et choisis la variable correspondante. Tous les calques de cette couleur sont reliés d'un coup.
