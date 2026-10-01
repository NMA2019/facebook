# Feuille de route — Guide Facebook

Cette feuille de route décrit les évolutions envisagées pour le guide. Elle n'est pas un engagement contractuel : les priorités peuvent évoluer selon les retours des utilisateurs et les changements d'interface de Meta.

Légende : ✅ livré · 🚧 en cours · 📋 planifié · 💡 à l'étude

---

## Vision

Maintenir un **guide de référence francophone** sur la gestion professionnelle d'une Page Facebook, qui reste :

- **fiable** — le contenu suit l'évolution réelle de l'interface Meta ;
- **accessible** — utilisable sur téléphone, hors ligne et sans JavaScript ;
- **simple à maintenir** — un seul fichier, aucune dépendance à installer.

---

## Version 1.1 — Confort d'usage 📋

- 💾 **Persistance de la progression** : mémoriser les étapes cochées dans le `localStorage` du navigateur, avec un bouton « réinitialiser ».
- 🔗 **Partage de la progression** : générer un lien encodant l'état des cases cochées (utile pour un formateur qui suit un groupe).
- 🖨️ **Export PDF propre** : feuille de styles d'impression dédiée, avec en-tête et numéros de page.
- 🔍 **Recherche interne** : champ de recherche filtrant les étapes et chapitres par mot-clé.
- 🌙 **Thème sombre** : respect de `prefers-color-scheme: dark` et bascule manuelle.

## Version 1.2 — Contenu enrichi 📋

- ✍️ **Chapitre « Modèles et exemples »** : exemples de bios, de catégories, de calendriers éditoriaux prêts à l'emploi.
- 🗓️ **Chapitre « Calendrier 4 semaines »** : planning type détaillé, semaine par semaine.
- 💰 **Chapitre « Fiscalité et reversements »** : cadre général sur les revenus publicitaires et les obligations déclaratives (avec avertissement clair).
- ❓ **FAQ étendue** : nouveaux cas de dépannage (récupération de compte, litige de nom, blocage pays).
- 📊 **Glossaire** : définitions des termes Meta (portée, ensemble de publicités, pixel, Advantage+…).

## Version 1.3 — Internationalisation 💡

- 🌍 **Structure i18n** : externalisation des chaînes de texte.
- 🇬🇧 **Version anglaise** à titre exploratoire.
- 📐 **Textes RTL** : compatibilité arabe si la demande existe.

## Version 2.0 — Outillage 💡

- ⚛️ **Refonte optionnelle** vers un projet à composants (React ou Vite + HTML) **tout en conservant un export « fichier unique »** pour le déploiement simple.
- 📱 **Application mobile wrappée** (PWA) : utilisable hors ligne avec icône sur l'écran d'accueil.
- 🔌 **Aide contextuelle** : info-bulles détaillées et renvois vers la documentation officielle Meta.
- ♿ **Audit d'accessibilité complet** (WCAG 2.2 AA) avec corrections documentées.

---

## Maintenance continue 🚧

Tâche permanente, à chaque évolution notable de Meta :

- [ ] Mettre à jour les **libellés de menus** (Facebook, Business Suite, Gestionnaire de publicités).
- [ ] Vérifier les **seuils de monétisation** et les conditions d'éligibilité.
- [ ] Réviser les **objectifs de campagne** et les formats recommandés.
- [ ] Corriger les **erreurs de lien** (URL des outils Meta).
- [ ] Vérifier l'affichage **mobile / tablette / ordinateur**.
- [ ] Tester **avec et sans JavaScript**.
- [ ] Consigner chaque changement dans [CHANGELOG.md](CHANGELOG.md).

---

## Non-objectifs (hors périmètre)

Pour rester clair et maintenable, le projet **ne vise pas** à :

- fournir un **service client** ou un support de compte Meta ;
- garantir des **résultats** (revenus, certification, performance publicitaire) ;
- remplacer la **documentation officielle** de Meta ;
- collecter des **données utilisateurs** ou intégrer un back-end.

---

## Comment proposer une évolution

Ouvrez une demande en précisant :

1. **Le besoin** — quel problème cela résout pour l'utilisateur.
2. **La cible** — un chapitre, la navigation, l'accessibilité, le déploiement…
3. **La contrainte** — rester dans un fichier autonome si possible.

Les propositions alignées avec la vision (« fiable, accessible, simple ») seront priorisées.