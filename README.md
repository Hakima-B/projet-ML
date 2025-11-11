# Projet Machine Learning : Prédiction du prix des maisons

##  Objectif
Créer un modèle capable de **prédire le prix des maisons** en fonction de leurs caractéristiques (superficie, nombre de pièces, quartier, type de logement, état, année de construction, équipements, etc.).

Ce projet couvre toutes les étapes typiques d’un workflow Data Science :
- Création d’un dataset réaliste
- Exploration et visualisation des données
- Nettoyage et feature engineering
- Modélisation et évaluation
- Fonction finale de prédiction

---

##  Technologies utilisées
- **Python 3**  
- Librairies :
  - `pandas` & `numpy` pour la manipulation de données  
  - `matplotlib` & `seaborn` pour la visualisation  
  - `scikit-learn` pour le Machine Learning (`LinearRegression`, `RandomForestRegressor`)  

---

##  Dataset
- **Nombre de maisons simulées** : 800  
- **Variables principales** :  
  - `superficie_m2`, `nb_pieces`, `quartier`, `type_logement`, `etat`  
  - `annee_construction`, `balcon`, `garage`, `proximite_metro`, `prix`  

- Injection de valeurs manquantes et ajout de features supplémentaires :
  - `age_maison`, `prix_m2`, `surface_par_piece`, `score_commodite`, `categorie_superficie`

---

##  Exploration & Visualisations
- Distribution des prix et par quartier  
- Corrélation entre variables numériques  
- Relation superficie vs prix, prix par type de logement  
- Analyse des outliers et nettoyage des données

---

## 🤖 Modélisation
- **Régression Linéaire Multiple**
  - R² Test : ~0.449
  - MAE : ~314,160€
  - RMSE : ~417,231€
- **Random Forest**
  - R² Test : ~0.763
  - MAE : ~204,715€
  - RMSE : ~273,759€
- **Variables les plus importantes** : `superficie_m2`, `quartier_encoded`, `type_logement_encoded`, `etat_encoded`

---

# Fonction de prédiction
Exemple d’utilisation :

```python
predire_prix_maison(
    superficie=150,
    nb_pieces=5,
    quartier='Zone résidentielle',
    type_logement='Maison',
    etat='Neuf',
    annee_construction=2020,
    balcon=1,
    garage=1,
    proximite_metro=0
)
# Résultat attendu : ~1,562,000€
