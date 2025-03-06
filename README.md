# projetdata25
Projet Data DDEFI (Prédiction Over/Under du Nombre d'Aces en Tennis)


## A/ Introduction
Ce projet vise à développer un modèle de machine learning permettant de prédire si le nombre d'aces dans un match de tennis sera au-dessus ou en dessous d'un seuil donné. En exploitant des données historiques de matchs et des caractéristiques des joueurs avec notre modèle, notre objectif est d'améliorer la précision des prédictions pour aider les parieurs et les 
opérateurs de paris sportifs.

Les données sur les matches ATP sont issues du github de JeffSackmann : https://github.com/JeffSackmann/


## B/ Installation
### 1. Prérequis à installer
Assurez-vous d'avoir installé les éléments suivants :
- **Python 3.8 ou plus**
- **Git**
- **Jupyter Notebook**

### 2. Cloner le dépôt
Commencez par récupérer le projet en clonant le dépôt GitHub :
```bash
git clone https://github.com/mathias1376/projetdata25
cd projetdata25
```

### 3. Créer un environnement virtuel et installer les dépendances
Nous recommandons d'utiliser un environnement virtuel pour isoler les dépendances du projet :
```bash
python -m venv venv
source venv/bin/activate  # Sur Windows : venv\Scripts\activate
pip install -r requirements.txt
```

## C/ Utilisation
### 1. Exécution du Notebook
Le projet est implémenté sous forme de notebook Jupyter (`code_final.ipynb`). Pour l'exécuter localement :
```bash
jupyter notebook
```
Puis ouvrez `code_final.ipynb` et exécutez les cellules dans l'ordre.


### 2. Structure du projet
```
/
|-- ML_Documentation/           # Explication de notre modèle, de notre démarche, de notre réflexion et de nos résultats avec leurs analyses.
|-- README.md/                  # Documentation technique pour utiliser notre modèle de machine learning.
|-- atp_matches_2023.csv        # Pipeline de données exploitable.
|-- code_final.ipynb            # Code source dans son intégralité.
|-- preprocess.ipynb            # Ebauches ayant servi à construire le code final.
|-- processed_tennis_data.csv   # Données brutes extraites pour notre modèle.
```

### 3. Fonctionnement du Modèle

1. **Chargement des données** :
   - Les données de matchs de tennis sont chargées via `pandas` à partir du fichier CSV `atp_matches_2023.csv`.
   - Vérification des variables pour avoir une idée globale de ce qu'on traite.

2. **Exploration des données** :
   - Création de différents graphiques (comme la distribution d'aces par match ou du nombre d'aces en fonction de la surface).
   - Matrice de corrélation.

3. **Prétraitement des données** :
   - Sélection et visualisation des variables influentes via la méthode LASSO.
   - Normalisation des données pour améliorer la convergence du modèle.

4. **Séparation des données** :
   - Division en ensemble d'entraînement (80%) et de test (20%) avec `train_test_split`.

5. **Modélisation** :
   - Test de plusieurs algorithmes de Machine Learning, notamment :
     - En premier lieu avec **Random Forest** pour une première approche simple mais robuste avec **LASSO Regression** pour une meilleure sélection.
     - En deuxième lieu avec **Random Forest** et **LASSO Regression** avec plus de variables et d'autres selections.
     - Enfin avec **XGBoost** pour comparaison avec **Random Forest**

6. **Exploration approfondie des données** :
   - Création de graphiques plus précis, comme la proportion d'aces par nationalité ou par tranche d'âge ou du type de best of (3 ou 5).
   - Essais de modélisation sur davantage de variables (âge, taille, historique des 10 derniers matchs...)
  
7. **Prédiction et validation** :
   - Génération des prédictions sur l'ensemble de test.
   - Évaluation via `classification_report` et `confusion_matrix`.
   - Ajustement des hyperparamètres pour améliorer la précision du modèle.



