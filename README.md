# 🧀 Concevez une application au service de la santé publique

Nettoyage et analyse exploratoire d'un jeu de données nutritionnelles issu d'Open Food Facts (catégorie fromages), en vue de la conception d'une application aidant les usagers à mieux s'alimenter.

## 📌 Contexte

L'agence **Santé publique France** souhaite exploiter le jeu de données ouvert **Open Food Facts** pour, à terme, proposer une application permettant d'améliorer les habitudes alimentaires des utilisateurs. Avant toute idée d'application, il est nécessaire d'évaluer la qualité de ce jeu de données, de le nettoyer, puis de l'explorer pour identifier les variables pertinentes et les relations qui pourraient être exploitées.

## 🎯 Objectifs

- Sélectionner un sous-ensemble de produits pertinent (ici, la catégorie des **fromages**) et les variables nutritionnelles à étudier.
- Traiter les valeurs manquantes, aberrantes et atypiques du jeu de données.
- Imputer les valeurs manquantes restantes selon plusieurs stratégies (médiane, régression linéaire, k plus proches voisins).
- Réaliser une analyse exploratoire univariée, bivariée et multivariée des variables nutritionnelles.
- Étudier les liens entre variables quantitatives et le Nutri-Score (ACP, ANOVA).

## 🗂️ Données

Le projet s'appuie sur un extrait du jeu de données ouvert **[Open Food Facts](https://world.openfoodfacts.org/)**, filtré sur la catégorie des fromages (1732 produits dans l'échantillon étudié). Les données ne sont pas incluses dans ce dépôt.

## 📁 Structure du projet

| Fichier | Description |
|---|---|
| `sante_1_notebook_nettoyage.ipynb` | Sélection des produits et variables pertinentes, suppression des variables trop incomplètes ou corrélées, traitement des valeurs aberrantes (plafonnement des outliers) et imputation des valeurs manquantes (médiane, régression linéaire, kNN). Export du jeu de données nettoyé au format CSV. |
| `sante_2_notebook_exploration.ipynb` | Analyse exploratoire du jeu de données nettoyé : analyses univariée (histogrammes, camembert du Nutri-Score), bivariée (nuages de points), multivariée (heatmap de corrélation, ACP, cercles des corrélations) et test ANOVA entre variables quantitatives et Nutri-Score. |
| `sante_3_presentation.pptx` | Fichier de présentation. |

## 🧰 Technologies utilisées

- **Python**, **Pandas**, **NumPy**
- **Matplotlib**, **Seaborn**, **missingno** (visualisation, valeurs manquantes)
- **Scikit-learn** : `KNNImputer`, `linear_model` (régression linéaire), `PCA`, `StandardScaler`
- **SciPy** (`scipy.stats`) : test ANOVA

## 🔍 Démarche

1. **Sélection** : filtrage des produits sur la catégorie fromages, exclusion des fromages blancs, sélection des variables nutritionnelles pertinentes a priori.
2. **Nettoyage** : suppression des variables avec plus de 50 % de valeurs manquantes, vérification de la validité des plages de valeurs (taux entre 0 et 100, énergie positive, Nutri-Score entre A et E), suppression des variables trop corrélées (ex. sodium vs sel).
3. **Traitement des outliers** : détection par écart interquartile et boxplots, plafonnement des valeurs extrêmes plutôt qu'exclusion, avec vérification manuelle des cas les plus extrêmes sur Open Food Facts.
4. **Imputation des valeurs manquantes** : combinaison de trois méthodes selon les variables — valeur médiane/moyenne, régression linéaire entre variables corrélées (ex. matières grasses saturées à partir des matières grasses totales), puis imputation par k plus proches voisins (kNN) pour les dernières valeurs manquantes.
5. **Analyse exploratoire** : études univariée, bivariée et multivariée (heatmap, ACP avec cercles des corrélations, ANOVA) pour comprendre la structure des données et les variables discriminantes du Nutri-Score.

## 👤 Auteur

David Depouez — Projet réalisé dans le cadre de la formation *Ingénieur Machine Learning (OpenClassrooms, RNCP niv. 7)*.
