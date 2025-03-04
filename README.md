# projetdata25
Projet Data DDEFI (Prédiction Over/Under du Nombre d'Aces en Tennis)

## 1. Introduction
Ce projet vise à développer un modèle de machine learning permettant de prédire si le nombre d'aces dans un match de tennis sera au-dessus ou en dessous d'un seuil donné (Over/Under). En exploitant des données historiques de matchs et des caractéristiques des joueurs, notre objectif est d'améliorer la précision des prédictions pour aider les parieurs et les opérateurs de paris sportifs.

## 2. Installation
### 2.1. Prérequis
Avant d'exécuter le projet, assurez-vous d'avoir installé les éléments suivants :
- **Python 3.8 ou plus**
- **Git**
- **Jupyter Notebook**
- **Google Colab** (si vous souhaitez exécuter le notebook en ligne)

### 2.2. Cloner le dépôt
Commencez par récupérer le projet en clonant le dépôt GitHub :
```bash
git clone https://github.com/votre-repo.git
cd votre-repo
```

### 2.3. Créer un environnement virtuel et installer les dépendances
Nous recommandons d'utiliser un environnement virtuel pour isoler les dépendances du projet :
```bash
python -m venv venv
source venv/bin/activate  # Sur Windows : venv\Scripts\activate
pip install -r requirements.txt
```

## 3. Utilisation
### 3.1. Exécution du Notebook
Le projet est implémenté sous forme de notebook Jupyter (`code_final.ipynb`). Pour l'exécuter localement :
```bash
jupyter notebook
```
Puis ouvrez `code_final.ipynb` et exécutez les cellules dans l'ordre.

Si vous utilisez Google Colab, uploadez le fichier dans votre espace et exécutez les cellules une à une.

### 3.2. Structure du projet
```
/
|-- data/                    # Données brutes et transformées
|-- notebooks/               # Notebooks pour l'exploration et la modélisation
|-- src/                     # Code source
    |-- preprocessing.py     # Nettoyage et transformation des données
    |-- model.py            # Entraînement et évaluation du modèle
    |-- predict.py          # Fonction de prédiction
|-- requirements.txt         # Liste des dépendances
|-- README.md                # Documentation
```

### 3.3. Fonctionnement du Modèle
1. **Chargement des données** :
   - Le fichier `atp_matches_2023.csv` est téléversé dans Google Colab.
   - Les données sont chargées avec `pandas`.

2. **Exploration des données** :
   - Affichage des valeurs uniques de certaines colonnes pour comprendre la structure des données (nationalité, score, temps du match, etc.).

3. **Prétraitement des données** :
   - Nettoyage des valeurs manquantes.
   - Sélection des colonnes pertinentes pour la prédiction des aces.
   - Normalisation avec `StandardScaler`.

4. **Séparation des données** :
   - Division en ensemble d'entraînement et de test (80%-20%) avec `train_test_split`.

5. **Modélisation** :
   - Entraînement d'un `RandomForestClassifier` sur les données transformées.

6. **Prédiction et validation** :
   - Génération des prédictions sur l'ensemble de test.
   - Évaluation avec `accuracy_score` et `classification_report`.


