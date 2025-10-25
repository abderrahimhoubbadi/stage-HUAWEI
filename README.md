# Prédiction du Trafic Réseau 5G avec des Modèles Deep Learning 📶

![Python](https://img.shields.io/badge/Python-3.x-blue?style=for-the-badge&logo=python)![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=tensorflow)![Keras](https://img.shields.io/badge/Keras-D00000?style=for-the-badge&logo=keras)![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas)

Ce projet, développé dans le cadre d'un stage chez **Huawei Technologies**, présente une solution de Deep Learning pour prédire le trafic d'un réseau mobile 5G en se basant sur les données historiques d'un réseau 4G.

---

## 🎯 Contexte et Objectif

L'avènement de la 5G s'accompagne de défis majeurs en matière de gestion de réseau. Pour optimiser les ressources et garantir une qualité de service, il est crucial d'anticiper les futures demandes de trafic. Cependant, le manque de données historiques pour la 5G rend la modélisation directe difficile.

L'objectif de ce projet est de surmonter ce défi en développant un modèle prédictif robuste qui exploite la richesse des données de trafic 4G existantes pour prévoir l'évolution du trafic 5G.

## 💡 Approche Méthodologique

La solution repose sur une approche de modélisation de séries temporelles utilisant un réseau de neurones profond. Le pipeline se décompose comme suit :

1.  **Ingénierie des Caractéristiques (Feature Engineering)**
    *   La saisonnalité du trafic réseau est un facteur clé. Pour la capturer, les données temporelles sont transformées en composantes cycliques (sinusoïdales et cosinusoïdales) afin de modéliser les tendances **quotidiennes, mensuelles et annuelles**.

2.  **Simulation de la Croissance 5G**
    *   Pour simuler la transition de la 4G à la 5G, une **hypothèse d'augmentation de capacité de 330%** a été appliquée aux données. Cette projection est basée sur les estimations industrielles de la croissance de la demande et de la capacité accrue des réseaux de nouvelle génération.

3.  **Modèle de Deep Learning : LSTM Bidirectionnel**
    *   Un réseau de neurones récurrents de type **LSTM Bidirectionnel** a été choisi pour sa capacité à analyser les dépendances séquentielles dans les deux directions (passé vers futur et futur vers passé), ce qui est idéal pour capturer les motifs complexes des séries temporelles.
    *   **Architecture du modèle** :
        *   Couche d'entrée
        *   Deux couches LSTM Bidirectionnelles (128 et 64 unités)
        *   Couches `Dense` avec activation ReLU et régularisation `Dropout` pour éviter le surapprentissage.
        *   Couche de sortie pour la prédiction.

## 📊 Visualisation des Résultats

Les visualisations montrent une excellente adéquation du modèle sur les données d'entraînement, de validation et de test, ainsi qu'une prédiction future cohérente avec les tendances apprises.

*(Conseil : Ajoutez ici une capture d'écran de la Figure 3.1 ou 3.2 de votre rapport pour un impact visuel maximal !)*
![Aperçu des Prédictions](URL_DE_VOTRE_IMAGE_DE_PREDICTION.png)

L'interprétation des courbes confirme que :
-   Le modèle apprend efficacement les tendances des données historiques.
-   Il généralise bien sur des données non vues.
-   Il fournit des prévisions précieuses pour une gestion proactive du réseau 5G.

---

## 🛠️ Stack Technique

-   **Langage** : Python
-   **Deep Learning** : TensorFlow, Keras
-   **Analyse de Données** : Pandas, NumPy
-   **Pré-traitement** : Scikit-learn (`StandardScaler`)
-   **Visualisation** : Matplotlib
-   **Interface Fichiers** : Tkinter

---

## 🚀 Comment Lancer le Projet

Le projet est un script Python qui utilise une interface `Tkinter` pour sélectionner les fichiers de données.

### Prérequis
-   Python 3.8+ et Pip
-   Un environnement virtuel est fortement recommandé.

### Installation

1.  **Clonez ce dépôt :**
    ```bash
    git clone https://github.com/VOTRE_NOM_UTILISATEUR/5G-Traffic-Prediction.git
    cd 5G-Traffic-Prediction
    ```

2.  **Créez et activez un environnement virtuel :**
    ```bash
    python -m venv venv
    # Sur Windows:
    # venv\Scripts\activate
    # Sur macOS/Linux:
    # source venv/bin/activate
    ```

3.  **Installez les dépendances :**
    *(Conseil : Créez un fichier `requirements.txt` avec les librairies listées dans le rapport pour faciliter l'installation)*
    ```bash
    pip install tensorflow pandas numpy scikit-learn matplotlib
    ```

### Exécution

1.  **Lancez le script principal :**
    ```bash
    python Model.py
    ```

2.  **Suivez les instructions :**
    *   Une première fenêtre de dialogue s'ouvrira pour vous demander de **sélectionner le fichier CSV des données historiques (4G)**.
    *   Une seconde fenêtre s'ouvrira pour **sélectionner le fichier CSV des données futures**.
    *   Dans le terminal, vous serez invité à entrer les noms des colonnes (date, features, cible).
    *   Le script exécutera alors l'entraînement, l'évaluation et affichera le graphique des prédictions.

---

## 📂 Structure du Dépôt

```
.
├── stage.ipynb               # Le script principal contenant tout le pipeline
└── README.md
```

---

## 🙏 Remerciements

Ce travail a été réalisé dans le cadre de mon stage chez **Huawei Technologies**. Je tiens à remercier mes encadrants, **Mr. Chefaj Jawad** et **Mr. Amine**, pour leur soutien constant et leurs précieux conseils tout au long de cette expérience enrichissante.
