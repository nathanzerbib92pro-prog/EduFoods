# EDUFOODS — historique du projet (cours EFREI)

Récupéré le 2026-10-16 depuis la conversation Claude partagée
https://claude.ai/share/6f2ba889-aefb-4936-8bc5-a06c31225201 (échanges des 24 et 29 sept. 2026).
Les images envoyées dans la conversation (consignes du cours, exemple CargoCycle…) étaient masquées dans le partage : non récupérées.

## Rangement du dossier
- `01-cahier-des-charges/` : `Cahier_des_charges_EDUFOODS.docx`
- `02-architecture-reseau/` : `Architecture_SI_EDUFOODS.png`, `Schema_reseau_EDUFOODS.png`
- `03-planning/` : `Planning_EDUFOODS.xlsx` (Gantt), `Gantt_EDUFOODS.png`
- `04-maquettes/` : `maquettes_EDUFOODS.zip` (version finale), planche d'ensemble, carte du prototype
  - `ecrans-svg/` : contenu du zip — 14 SVG, `Plugin_Figma_EDUFOODS.zip`, `EDUFOODS_couleurs.tokens.json`, `LISEZ-MOI.md`
  - `palettes/` : comparatif + palettes A à E (A retenue)

## Le projet
- Projet **seul**.
- Le cours impose : un cahier des charges en 6 parties (modèle de l'exemple « CargoCycle »), **18 contraintes obligatoires**,
  une application web reliée à une base de données **et** à un service externe, un site vitrine,
  et l'infrastructure d'une entreprise d'au moins 10 utilisateurs (tickets ITIL, sauvegarde, gestion des accès, supervision…).
- Objectif : permettre aux étudiants de manger sainement le midi à prix réduit grâce aux commandes groupées.

## Choix validés
- **Entreprise** : startup de 12 salariés à Paris — direction (2), partenariats restaurants (3), support client (2),
  marketing/communication (2), administration/comptabilité (1), informatique (2).
  Chauffeurs indépendants (non salariés) qui utilisent l'application.
- **Zone** : campus parisiens au lancement, puis d'autres villes étudiantes.
- **Modèle économique** : commission sur chaque commande côté restaurant + petits frais de service étudiants, réduits par le regroupement.
- **Situation de départ** : commandes groupées via WhatsApp et Google Forms, suivi sur Excel → ingérable quand le volume augmente.
- **Commandes groupées** : regroupement automatique (même restaurant, même créneau, même point de livraison/retrait),
  ou un étudiant crée un groupe et invite ses amis.
- **Livraison** : retrait sur place ou livraison par des chauffeurs indépendants.
- **Application étudiant** : application web + PWA (l'app mobile native est classée « Won't » dans le MoSCoW).
- **Paiement** : en ligne avec Stripe (c'est le service externe exigé par les contraintes).
- **Vérification étudiante** : adresse mail étudiante ou carte étudiante.
- **Fonctionnalités en plus** : filtres « plats sains » et « petit budget », notes et avis, suivi de commande en temps réel,
  historique, fidélité (optionnel).

## Livrables déjà produits
1. **Cahier des charges** (DOCX, 8 pages) : les 6 parties du cours, les 18 contraintes en partie 6, tableau MoSCoW en partie 5.
2. **Architecture du SI** (PNG) : 5 couches (utilisateurs, accès, services, données, exploitation) ;
   services externes à droite (Stripe, cartographie, e-mails, stockage cloud).
3. **Schéma réseau** (PNG), avec le plan d'adressage IP sur les machines :
   - DMZ (VLAN 20) : reverse proxy, site vitrine, 2 serveurs d'application (le 2e pour la continuité de service) ;
   - LAN serveurs (VLAN 10) : annuaire, base de données + réplique, tickets, fichiers, supervision, NAS de sauvegarde ;
   - LAN utilisateurs : un VLAN par usage (salariés, admin IT, Wi-Fi salariés, Wi-Fi invités).
4. **Planning** : 10 semaines, du 28/09 au 04/12/2026, 30 tâches en 6 phases, chaque tâche reliée à sa contrainte obligatoire.
   Gantt automatique par jour ouvré (jours fériés exclus ; cellules bleues modifiables), onglet « Indicateurs »
   (avancement global, tâches terminées, en retard → contraintes 14 et 15). L'image Gantt ne se met pas à jour toute seule.
5. **Maquettes haute fidélité** — 14 SVG à importer dans Figma :
   - étudiant mobile (6) : accueil, restaurant + menu, panier groupé (jauge de réduction), paiement, suivi de commande, profil/historique ;
   - étudiant ordinateur (1) : accueil ;
   - chauffeur mobile (2) : livraisons disponibles, livraison en cours ;
   - restaurant ordinateur (2) : tableau de bord des commandes groupées, gestion du menu et des offres de gros ;
   - back-office ordinateur (2) : statistiques, gestion des restaurants et des utilisateurs ;
   - site vitrine ordinateur (1) : accueil.
   - **Plugin Figma** (« Tout faire ») : crée la collection de variables « EDUFOODS » (groupes Marque, Neutres, États ; 12 couleurs),
     relie chaque calque à sa variable, et crée le prototype : 32 liens, 5 parcours (étudiant mobile, chauffeur, restaurant,
     back-office, site vitrine), défilement du site vitrine (900 px). Testé seulement sur une simulation de Figma.

## Identité visuelle (palette A)
- Logo « edufoods » en minuscules, icône feuille + fourchette.
- Principal vert `#2BB673`, accent orange `#FF8A3D`, texte bleu nuit `#1E2A38`, fond blanc cassé `#F7F9F6`.
- Polices : Poppins (titres), Inter (texte). Ambiance jeune et healthy, coins arrondis, cartes aérées.
- Contenu fictif : restaurants Green Bowl, Poké Campus, La Fabrique à Salades, Chez Momo ; plats de 6 à 10 € ;
  points de retrait sur des campus parisiens.

## Pistes évoquées, pas encore faites
- Écran d'inscription avec vérification de la carte étudiante.
- Mode sombre.
