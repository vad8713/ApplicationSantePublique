# 🧀 Application pour la Santé Publique — Analyse Nutritionnelle des Fromages

## 📌 Contexte
Projet réalisé dans le cadre de la formation Ingénieur Machine Learning
(OpenClassrooms, RNCP niv. 7).

L'objectif est d'explorer la base de données Open Food Facts afin
d'identifier des indicateurs nutritionnels pertinents pour une application
de santé publique, en se concentrant sur la famille des fromages.

## 🎯 Objectif
Analyser la composition nutritionnelle de fromages (lait cru, thermisé
et pasteurisés) pour dégager des tendances, identifier des variables
explicatives du Nutri-Score, et produire des visualisations exploitables
par une application grand public.

## 🛠️ Stack technique
- **Langage** : Python
- **Librairies** : Pandas, NumPy, Matplotlib, Seaborn, SciPy, Missingno
- **Environnement** : Jupyter Notebook

## 📊 Approche

### Notebook 1 — Nettoyage des données
1. Import de la base Open Food Facts (320 772 produits, 162 variables)
2. Filtrage sur les fromages : lait cru, thermisé, pasteurisés → **1 732 produits**
3. Sélection de 27 variables nutritionnelles pertinentes
   (énergie, graisses, protéines, sel, vitamines, minéraux...)
4. Traitement des valeurs manquantes (visualisation via Missingno)

### Notebook 2 — Exploration des données
1. **Analyse univariée** : distribution du Nutri-Score (majoritairement D),
   histogrammes avec moyennes et médianes pour chaque variable quantitative
2. **Analyse bivariée** : nuages de points croisant l'énergie avec
   les autres variables nutritionnelles

## 📈 Résultats clés
- **89 %** des fromages ont un Nutri-Score D ou E (produits peu favorables)
- Les graisses saturées et l'énergie sont fortement corrélées
- Les protéines constituent un signal nutritionnel positif
  pour différencier les fromages

## 📁 Structure du repo
ApplicationSantePublique/  
├── sante_1_notebook_nettoyage.ipynb # Nettoyage et préparation  
├── sante_2_notebook_exploration.ipynb # Analyse exploratoire  
└── README.md
