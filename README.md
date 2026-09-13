# Analyse du marché de l'emploi Tech en France

Projet de Data Analysis et Data Science visant à analyser les tendances du marché de l'emploi Tech en France à partir d'offres d'emploi.

## Objectifs

L'objectif de ce projet est d'explorer le marché de l'emploi Tech afin de mieux comprendre :

- la répartition des offres par métier et par zone géographique ;
- les compétences techniques les plus recherchées ;
- les tendances salariales ;
- les facteurs associés aux niveaux de rémunération ;
- la demande relative pour différentes compétences Tech.

Le projet couvre plusieurs étapes d'un pipeline Data Science, de la préparation des données jusqu'à la modélisation et à la création d'indicateurs.

## Technologies utilisées

- Python
- pandas
- NumPy
- scikit-learn
- Matplotlib
- SQL
- Jupyter Notebook

## Structure du projet

### 1. Préparation des données
`01_preparation_dataframe_jupyter.ipynb`

Nettoyage, structuration et préparation du jeu de données avant analyse.

### 2. Analyse exploratoire
`02_EDA_geographic_areas.ipynb`

Analyse des offres selon plusieurs dimensions :

- métiers ;
- types de contrats ;
- localisation ;
- salaires ;
- tendances générales du marché.

### 3. Extraction des compétences
`03_extraction_competences.ipynb`

Extraction automatique des compétences techniques présentes dans les intitulés et descriptions d'offres.

Cette étape permet notamment d'identifier les technologies les plus demandées sur le marché et d'observer les différences entre plusieurs métiers Data.

### 4. Analyse et prédiction des salaires
`04_prediction_salaires.ipynb`

Exploration des facteurs associés aux niveaux de rémunération et expérimentation de modèles de Machine Learning pour la prédiction salariale.

Cette étape est principalement exploratoire en raison du nombre limité d'offres disposant d'une information salariale exploitable.

### 5. Tech Skills Index
`05_tech_skills_index.ipynb`

Construction d'un indicateur composite visant à comparer la demande pour différentes compétences techniques sur le marché de l'emploi.

## Résultats et enseignements clés

### Marché de l'emploi Tech

L'analyse exploratoire met notamment en évidence que :

- **67,4 % des offres étudiées sont proposées en CDI** ;
- les métiers **Data Engineer** et **Data Analyst** figurent parmi les plus représentés ;
- les offres sont fortement concentrées dans certaines zones géographiques ;
- environ **85 % des offres ne renseignent pas de salaire**, ce qui limite fortement les analyses salariales.

Cette forte proportion de valeurs manquantes sur les salaires constitue un biais important à prendre en compte dans l'interprétation des résultats.

### Compétences les plus demandées

L'extraction automatique des compétences met en évidence plusieurs technologies particulièrement présentes dans les offres :

- **SQL : 35,4 %**
- **Git : 35 %**
- **Python : 33,9 %**
- **Tableau : 23,1 %**
- **Power BI : 21,4 %**

Les offres qui mentionnent des compétences en citent généralement **entre 3 et 5**.

L'analyse par métier fait également apparaître des profils de compétences différents :

- les offres **Data Engineer** sont fortement associées à SQL, Python et Git ;
- les offres **Data Scientist** mettent davantage en avant Python et les méthodes de Machine Learning ;
- les offres **Data Analyst** sont plus fortement liées aux outils de visualisation et de reporting.

Ces résultats permettent d'observer les différences entre les principaux profils du marché Data.

### Analyse textuelle et limites de l'extraction

L'extraction des compétences repose principalement sur une approche par dictionnaire.

Certaines offres ne contiennent donc aucune compétence détectée, alors qu'elles peuvent mentionner des technologies sous une forme différente ou utiliser des formulations absentes du dictionnaire.

Cette observation met en évidence une limite de l'approche utilisée.

Une amélioration possible serait d'utiliser des méthodes NLP plus avancées, par exemple :

- reconnaissance d'entités nommées (NER) ;
- modèles de langage ;
- embeddings ;
- classification automatique de compétences.

### Prédiction salariale

Une expérimentation de Machine Learning a été menée afin d'étudier la possibilité de prédire le salaire d'une offre à partir de différentes caractéristiques.

Les performances obtenues restent limitées, principalement en raison :

- du faible nombre d'offres avec salaire renseigné ;
- de la taille réduite de l'échantillon d'entraînement ;
- du biais de sélection lié aux valeurs manquantes.

Les modèles obtenus ne sont donc pas présentés comme des modèles prédictifs finaux.

Cette étape permet néanmoins d'étudier les variables potentiellement associées aux niveaux de rémunération et surtout d'illustrer l'importance de la qualité et du volume des données lors de la construction d'un modèle de Machine Learning.

## Tech Skills Index

Afin d'obtenir un indicateur plus robuste que la seule prédiction salariale, un score composite a été construit.

Il combine notamment :

- la fréquence d'apparition d'une compétence dans les offres ;
- son association avec les niveaux de rémunération observés.

L'objectif est d'identifier les compétences combinant demande du marché et potentiel de valorisation.

L'analyse permet ainsi de distinguer :

- des compétences très demandées sur le marché ;
- des compétences plus spécialisées ;
- des technologies de niche pouvant présenter un potentiel de valorisation plus élevé.

Parmi les compétences étudiées, des technologies comme **Tableau, GCP, TensorFlow, Scala et Spark** ressortent selon différents compromis entre fréquence d'apparition et signal salarial.

Ces résultats doivent néanmoins être interprétés avec prudence en raison du faible nombre d'offres disposant d'informations salariales.

## Limites du projet

Plusieurs limites doivent être prises en compte dans l'interprétation des résultats :

- une part importante des offres ne renseigne pas le salaire ;
- certaines catégories de métiers disposent de peu d'observations ;
- l'extraction des compétences dépend du dictionnaire utilisé ;
- les résultats reflètent uniquement les offres présentes dans la source de données utilisée ;
- certaines technologies ou certains profils spécialisés peuvent être davantage recrutés sur d'autres plateformes.

Ces limites ont été prises en compte dans l'interprétation des analyses et dans le choix de ne pas présenter la prédiction salariale comme un modèle final.

## Compétences mobilisées

- Data Cleaning
- Exploratory Data Analysis
- Data Visualization
- Feature Engineering
- Traitement de données textuelles
- Machine Learning
- Analyse statistique
- Interprétation de résultats
- Construction d'indicateurs
- Analyse critique des performances et limites d'un modèle

## Fichiers de données et résultats

Le repository contient également plusieurs fichiers CSV issus des différentes étapes du projet, notamment :

- `offres_emploi_tech_clean.csv`
- `offres_emploi_tech_eda.csv`
- `competences_offres.csv`
- `statistiques_competences.csv`
- `resultats_modeles_salaires.csv`
- `predictions_salaires_test.csv`
- `importance_variables_salaires.csv`
- `recommandations_competences.csv`
- `tech_skills_index.csv`

## Pistes d'amélioration

Plusieurs évolutions pourraient permettre d'approfondir le projet :

- améliorer l'extraction des compétences grâce à des méthodes NLP plus avancées ;
- utiliser des modèles NER avec spaCy ou Transformers ;
- intégrer de nouvelles sources d'offres d'emploi afin d'obtenir une vision plus représentative du marché ;
- automatiser la collecte et la mise à jour des données ;
- réaliser une analyse temporelle de l'évolution des compétences recherchées ;
- augmenter le volume de données salariales afin d'améliorer la modélisation ;
- développer un dashboard interactif avec Power BI ou Streamlit ;
- comparer l'évolution de la demande entre plusieurs métiers Data.

## Auteur

**Maysara Mellak**

Étudiante en Data Sciences & Intelligence Artificielle, avec une double compétence en Statistiques et Informatique.
