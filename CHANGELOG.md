# Journal des modifications — Guide Facebook

Toutes les modifications notables de ce projet sont documentées dans ce fichier.

Le format s'inspire de [Keep a Changelog](https://keepachangelog.com/fr/1.1.0/) et le projet adhère au [versionnage sémantique](https://semver.org/lang/fr/).

Types de changements utilisés :

- **Ajouté** : nouvelles fonctionnalités ou contenus.
- **Modifié** : changements dans le comportement ou le contenu existant.
- **Corrigé** : corrections de bugs ou d'erreurs factuelles.
- **Supprimé** : éléments retirés.
- **Sécurité** : correctifs liés à la sécurité.

---

## [Non publié]

### À venir
- Persistance de la progression des étapes (voir [ROADMAP.md](ROADMAP.md)).
- Recherche interne et export PDF dédié.

---

## [1.0.0] — 2026-01-10

Première version stable du guide, contenant le tutoriel complet en sept chapitres.

### Ajouté
- **Page unique autonome** `index.html` : HTML, CSS et JavaScript inclus, sans dépendance à installer.
- **Chapitre 0 — Avant de commencer** : liste des pré-requis (compte personnel réel, double authentification, e-mail professionnel, nom et catégorie, logo et couverture, informations de contact).
- **Chapitre 1 — Créer la Page** : ouverture de l'outil de création, champs de départ, logo et couverture, informations complémentaires, nom d'utilisateur, premières publications.
- **Chapitre 2 — Ajouter un administrateur** : tableau des types d'accès Meta, procédure d'ajout, activation du contrôle total, acceptation de l'invitation, bonnes pratiques de sécurité.
- **Chapitre 3 — Rendre la Page officielle** : distinction entre Page cohérente, vérification de l'entreprise et Meta Verified (badge bleu), avec procédures détaillées pour chacune.
- **Chapitre 4 — Activer Meta Business Suite** : connexion, portefeuille d'entreprise, connexion Instagram/WhatsApp, invitation de l'équipe, application mobile.
- **Chapitre 5 — Activer la monétisation** : conditions générales, sources de revenus (Content Monetization, Stars, abonnements, contenu de marque), activation pas à pas.
- **Chapitre 6 — Lancer une campagne publicitaire** : booster vs Gestionnaire de publicités, préparation du compte publicitaire, construction de la campagne en trois niveaux, objectifs, audience, budget, création et suivi.
- **Chapitre 7 — Faire grandir son audience** : définition de la cible, semaine type, Reels originaux, réponses rapides, communauté, mesure hebdomadaire, entretien de la Page.
- **Questions fréquentes** : sept cas de dépannage en accordéon.

### Ajouté (interface)
- **Sommaire dynamique** généré à partir des chapitres, horizontal sur mobile et latéral collant sur ordinateur.
- **Numérotation automatique** des chapitres et des étapes.
- **Cases à cocher de progression** avec barre de progression et compteur d'étapes terminées.
- **Mise en évidence du chapitre actif** au défilement (`IntersectionObserver`).
- **Tableaux adaptatifs** : transformés en cartes sur mobile, vrais tableaux dès 720 px.
- **Schémas dessinés en CSS** (maquettes de téléphone et d'écrans) sans image externe.
- **Bouton « retour en haut »** apparaissant au défilement.
- **Feuille de styles d'impression** masquant la navigation et les décorations.

### Ajouté (accessibilité)
- Structure de titres hiérarchisée (`h1` → `h3`).
- Attributs `aria-label`, `aria-current` et `aria-live` sur les éléments concernés.
- Styles `:focus-visible` visibles et contrastés.
- Respect de `prefers-reduced-motion`.
- Zones tactiles d'au moins 44 px.

### Ajouté (documentation)
- `README.md` : présentation, fonctionnalités, structure, prérequis, utilisation, personnalisation, accessibilité, contribution.
- `LICENSE` : licence MIT et avertissement de non-affiliation à Meta.
- `ROADMAP.md` : vision, versions planifiées, maintenance continue, non-objectifs.
- `CHANGELOG.md` : ce fichier.

### Note
- Les seuils, libellés et prix de Meta évoluent fréquemment ; le contenu est vérifié à la date indiquée en tête de chapitre et doit être recontrôlé régulièrement (voir la section « Maintenance continue » de [ROADMAP.md](ROADMAP.md)).

---

## Format des liens de version

- `[Non publié]` : changements en cours, non encore publiés.
- `[X.Y.Z]` : version publiée, avec sa date au format `AAAA-MM-JJ`.