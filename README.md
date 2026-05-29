# Comprendre le Deep RL — Les 3 familles d'algorithmes

Application web interactive expliquant les trois grandes familles d'algorithmes de l'**apprentissage par renforcement profond** (Deep Reinforcement Learning) : **DQN**, **Policy Network** et **Actor-Critic**.

Le projet transforme un cours théorique en une expérience visuelle où l'on peut **manipuler** chaque concept pour le comprendre.

---

## ▶ Comment l'ouvrir

Aucune installation requise.

1. Téléchargez le dossier du projet.
2. Double-cliquez sur le fichier **`index.html`**.
3. Le site s'ouvre directement dans votre navigateur.

> Le projet est un **fichier unique et autonome** (HTML + CSS + JavaScript). La seule ressource externe est la police d'écriture (Google Fonts) : avec une connexion, la typographie est complète ; sans connexion, le site reste parfaitement lisible grâce aux polices de secours.

---

## 🧭 Contenu — 5 onglets

| Onglet | Ce qu'il contient |
|--------|-------------------|
| **Vue d'ensemble** | Le problème commun à toutes les familles (état → action → récompense) et la présentation des trois approches. |
| **01 · DQN** | Méthode basée sur la valeur. Démo : le réseau apprend à noter chaque action + visualisation du Replay Buffer. |
| **02 · Policy** | Méthode basée sur la politique. Démo : la politique se forme par échantillonnage + cas continu (gaussienne). |
| **03 · Actor-Critic** | Méthode hybride. Démo : la boucle acteur ↔ critique avec calcul de l'avantage en temps réel. |
| **Comparaison** | Tableau comparatif des 3 familles + arbre de décision « quel algorithme choisir ? ». |

Chaque famille suit la même structure claire : **Comment ça marche** (étapes cliquables détaillées) → **Démo interactive** → **Quand l'utiliser** → **Algorithmes associés**.

---

## ✨ Fonctionnalités interactives

- **Étapes dépliables** : dans « Comment ça marche », chaque étape se clique pour révéler une explication approfondie (formules, astuces, intuitions).
- **Démo DQN** : lancez des étapes d'apprentissage et observez les notes Q converger vers la meilleure action (arg max), avec le Replay Buffer qui s'active.
- **Démo Policy** : échantillonnez des actions et voyez les probabilités s'ajuster ; manipulez la gaussienne pour le cas continu.
- **Démo Actor-Critic** : exécutez la boucle pas à pas et visualisez le calcul de l'avantage `A = (r + γ·V(s′)) − V(s)`.

---

## 🛠 Technologies

- **HTML5 / CSS3** (variables CSS, animations, design responsive)
- **JavaScript** (vanilla, sans bibliothèque externe)
- **SVG** pour la visualisation de la distribution continue

Aucun framework, aucune dépendance à installer.

---

## 📂 Structure du projet

```
projet-deep-rl/
├── index.html      ← l'application (ouvrir ce fichier)
└── README.md       ← ce fichier
```

---

## 🎨 Personnalisation

Tout est éditable directement dans `index.html` :

- **Textes des étapes** : dans les blocs `<div class="acc">` de chaque famille.
- **Données des démos** : dans les tableaux JavaScript en bas du fichier (`ACT`, `RW`, valeurs Q, etc.).
- **Couleurs** : dans les variables CSS en haut du fichier (`--amber`, `--violet`, `--teal`…).

---

## 🎯 Le concept pédagogique

Les trois familles forment une **progression logique** :

1. **DQN** apprend la *valeur* des actions, mais ne gère que les actions discrètes.
2. **Policy Network** apprend *directement* à agir (gère le continu), mais souffre d'une forte variance.
3. **Actor-Critic** corrige la variance du Policy en réimportant l'idée de valeur du DQN.

Le pont entre les trois est la **fonction d'avantage** : `A(s,a) = Q(s,a) − V(s)`.
