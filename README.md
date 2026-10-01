# Guide Facebook — Créer, certifier et monétiser sa Page

Tutoriel web **statique**, en **français**, qui explique pas à pas comment créer une Page Facebook, la sécuriser avec une équipe, la rendre officielle, activer Meta Business Suite, ouvrir la voie à la monétisation, lancer une campagne publicitaire et faire grandir son audience.

Le projet tient dans **un seul fichier autonome** : `index.html`. Aucune dépendance à installer, aucun back-end, aucune base de données. On l'ouvre dans un navigateur, et c'est tout.

> Guide indépendant, **non affilié à Meta**. Les noms de produits et de menus cités appartiennent à leurs propriétaires et peuvent changer sans préavis.

---

## Sommaire

- [Aperçu](#aperçu)
- [Fonctionnalités](#fonctionnalités)
- [Structure du projet](#structure-du-projet)
- [Prérequis](#prérequis)
- [Utilisation](#utilisation)
- [Personnalisation](#personnalisation)
- [Stack technique](#stack-technique)
- [Accessibilité](#accessibilité)
- [Compatibilité](#compatibilité)
- [Contenu éditorial](#contenu-éditorial)
- [Contribution](#contribution)
- [Licence](#licence)
- [Auteur](#auteur)

---

## Aperçu

Le guide est organisé en **chapitres numérotés automatiquement** et couvre l'ensemble du cycle de vie d'une Page professionnelle :

| # | Chapitre | Contenu |
|---|----------|---------|
| 0 | Avant de commencer | Pré-requis (compte réel, 2FA, e-mail pro, logo, couverture, coordonnées) |
| 1 | Créer la Page | Formulaire de création, nom, catégorie, bio, visuels, nom d'utilisateur |
| 2 | Ajouter un administrateur | Nouveaux types d'accès Meta, contrôle total / partiel, bonnes pratiques de sécurité |
| 3 | Rendre la Page officielle | Vérification de l'entreprise vs Meta Verified (badge bleu) |
| 4 | Activer Meta Business Suite | Portefeuille d'entreprise, connexion Instagram/WhatsApp, gestion d'équipe |
| 5 | Activer la monétisation | Conditions, programmes (Content Monetization, Stars, abonnements), mise en place |
| 6 | Lancer une campagne publicitaire | Booster vs Gestionnaire de publicités, objectifs, audience, budget, suivi |
| 7 | Faire grandir son audience | Planning éditorial, Reels, engagement, boucle de croissance |
| — | Questions fréquentes | Dépannage : accès manquant, refus de vérification, pub refusée, etc. |

---

## Fonctionnalités

- **100 % autonome** — un seul fichier `index.html`, CSS et JS inclus.
- **Mobile-first et responsive** — mises en page adaptées téléphone, tablette et ordinateur.
- **Sommaire dynamique** — le sommaire latéral (ou horizontal sur mobile) est généré à partir des chapitres présents dans le DOM.
- **Cases à cocher de progression** — chaque étape se coche ; une barre de progression indique le nombre d'étapes terminées.
- **Chapitre actif** mis en évidence au défilement via `IntersectionObserver`.
- **Schémas dessinés en CSS** — maquettes de téléphone et d'écrans, sans image externe.
- **Tableaux adaptatifs** — transformés en cartes sur petit écran, vrais tableaux au-delà de 720 px.
- **FAQ en accordéon** avec les éléments natifs `<details>` / `<summary>`.
- **Bouton « retour en haut »** apparaissant au défilement.
- **Mode impression** optimisé (masquage de la navigation et des fioritures).
- **Aucune dépendance JS externe** — tout est en JavaScript vanilla.
- **Polices Google Fonts** (Bricolage Grotesque + Public Sans) avec repli système.

---

## Structure du projet

```
facebook/
├── index.html   # L'application complète (HTML + CSS + JS)
├── README.md       # Ce fichier
├── LICENSE         # Licence du projet
├── ROADMAP.md      # Évolutions prévues
└── CHANGELOG.md    # Journal des modifications
```

Le fichier `index.html` est volontairement monolithique pour rester **déployable en un seul glisser-déposer** (hébergement statique, clé USB, partage par e-mail).

---

## Prérequis

- Un **navigateur web moderne** (Chrome, Firefox, Safari, Edge — versions récentes).
- **Aucune** installation : ni Node.js, ni PHP, ni base de données.
- Une **connexion à Internet** uniquement pour le chargement des polices Google Fonts (repli système automatique si hors ligne).

---

## Utilisation

### Ouverture locale

Double-cliquez sur `index.html`, ou depuis un terminal :

```bash
open index.html        # macOS
# xdg-open index.html  # Linux
# start index.html     # Windows
```

### Déploiement sur un serveur

Le fichier fonctionne tel quel sur n'importe quel serveur statique (Apache, Nginx, GitHub Pages, etc.). Exemple avec Nginx :

```nginx
server {
    listen 80;
    server_name mon-domaine.local;
    root /var/www/facebook;
    index index.html;

    location / {
        try_files $uri $uri/ /index.html;
    }
}
```

> Pensez à **activer HTTPS** en production et à définir un en-tête de sécurité adapté (CSP) si vous ajoutez des ressources externes.

---

## Personnalisation

### Ajouter un chapitre

Insérez un bloc `<section>` dans la section `<main>` (un emplacement dédié est prévu en commentaire dans le code) :

```html
<section class="chapitre" id="mon-chapitre" data-nav="Titre dans le sommaire">
  <h2><span class="ch-n"></span>Mon titre de chapitre</h2>
  <p class="intro">Introduction du chapitre.</p>
  <ol class="steps">
    <li class="step">
      <label class="mark"><input type="checkbox" aria-label="Marquer l’étape comme faite"><span class="num"></span></label>
      <div>
        <h3>Titre de l’étape</h3>
        <p>Description de l’étape.</p>
      </div>
    </li>
  </ol>
</section>
```

La **numérotation**, le **sommaire** et le **compteur d'étapes** se mettent à jour automatiquement (voir le JavaScript en bas du fichier).

### Modifier le thème

Toutes les couleurs sont centralisées dans les variables CSS `:root` :

| Variable | Usage |
|----------|-------|
| `--meta` / `--meta-deep` | Couleur principale (bleu Meta) |
| `--paper` / `--surface` | Fonds |
| `--ink` / `--muted` | Textes |
| `--ok` / `--warn` | États succès / avertissement |

---

## Stack technique

- **HTML5** sémantique.
- **CSS3** : variables, grille, flexbox, media queries, `:has()`, `prefers-reduced-motion`, `env(safe-area-inset-*)`.
- **JavaScript vanilla** (ES5 compatible) : génération du sommaire, étiquetage des tableaux, `IntersectionObserver`, barre de progression, bouton retour en haut.
- **Google Fonts** : `Bricolage Grotesque` (titres) et `Public Sans` (texte).

Aucune étape de build, aucun bundler, aucun transpileur.

---

## Accessibilité

- Structure de titres hiérarchisée (`h1` → `h3`).
- `aria-label` sur les éléments interactifs (cases à cocher, repères, sommaire).
- `aria-current="true"` sur le chapitre actif.
- `aria-live="polite"` sur le compteur de progression.
- Navigation clavier avec `:focus-visible` visible et contrasté.
- Respect de `prefers-reduced-motion` (désactivation du défilement fluide).
- Zones tactiles d'au moins 44 px.

Amélioration possible : la progression n'est **pas persistée** (elle est réinitialisée à chaque rechargement). Voir [ROADMAP.md](ROADMAP.md).

---

## Compatibilité

Testé et conçu pour les navigateurs modernes. Certaines fonctionnalités avancées (sélecteurs `:has()`, `IntersectionObserver`) nécessitent des versions récentes ; le contenu reste **lisible et complet** même sans JavaScript (les sections et étapes sont dans le HTML).

---

## Contenu éditorial

- Les **seuils, libellés de menus et prix** de Meta évoluent fréquemment : la seule source fiable reste l'interface réelle de l'utilisateur.
- Le guide **ne garantit aucun résultat** (revenus, certification, performance publicitaire).
- Le texte de l'interface est **entièrement en français**.

---

## Contribution

1. Créez une branche dédiée à votre modification.
2. Respectez le style existant (indentation 2 espaces pour le CSS/JS, conventions HTML du fichier).
3. Documentez tout changement notable dans [CHANGELOG.md](CHANGELOG.md).
4. Vérifiez l'affichage sur mobile **et** sur ordinateur, avec et sans JavaScript.
5. Ouvrez une demande de fusion en décrivant clairement le changement.

---

## Licence

Distribué sous licence **MIT**. Voir le fichier [LICENSE](LICENSE) pour le texte complet.

---

## Auteur

Projet réalisé dans le cadre de la créatrice/du créateur du dépôt `facebook`. Pour signaler une erreur factuelle (menu renommé, seuil obsolète), ouvrez une issue en indiquant la date et l'appareil concernés.