## El Baz Younes

<img src="El baz Younes 22007219 CAC 2.png" style="height:464px;margin-right:432px"/>

# CAC2

#22007219

# Description structurée de la base de données sur les portefeuilles pondérés

dataset_info = {
    "nom_du_createur": "I-Cheng Yeh",  # Créateur confirmé par la fiche descriptive de l'image [image:1]
    "date_de_creation": 2017,          # Date de création confirmée par l'article introductif et la fiche [image:1]
    "source_image": "image.jpg",       # Source visuelle du descriptif et métadonnées [image:1]
    "sujet": "Analyse de la performance des portefeuilles d'actions pondérés par concepts de sélection sur le marché américain", # Contexte scientifique [image:1][file:1]
    "structure": {
        "nombre_instances": 315,       # Nombre d'observations [image:1]
        "nombre_variables": 12,        # Nombre de caractéristiques quantitatives [image:1]
        "type_donnees": "Réelles",     # Toutes les variables sont quantitatives continues [image:1]
        "absence_valeurs_manquantes": True # Confirmé par la fiche descriptive [image:1]
    },
    "variables_principales": [
        "Large BP", "Large ROE", "Large SP", "Large Return Rate in the last quarter",
        "Large Market Value", "Small systematic Risk",
        "Annual Return", "Excess Return", "Systematic Risk", "Total Risk",
        "Abs. Win Rate", "Rel. Win Rate"
    ], # Concepts et métriques de performance [file:1]
    "cadre_temporel": "4 périodes de 5 ans de 1990 à 2010 (80 trimestres)", # Couverture temporelle [file:1]
    "critiques_modeles": [
        "Difficulté à identifier la meilleure combinaison de pondérations",
        "Optimisation systématique complexe",
        "Limites pour répondre aux profils variés d'investisseurs"
    ], # Limites méthodologiques [image:1]
    "licence": "Creative Commons Attribution 4.0", # Réutilisation ouverte [image:1]
    "reference_scientifique": "Using mixture design and neural networks to build stock selection decision support systems (Liu & Yeh, 2017)" # Article intro [image:1]
}

# Affichage détaillé
for cle, valeur in dataset_info.items():
    print(f"{cle} : {valeur}")
# Analyse structurée de la base de données des portefeuilles d'actions

stock_portfolio_dataset = {
    "nom_du_fichier": "stock-portfolio-performance-data-set-1.xlsx", # Fichier source [file:1]
    "structure": {
        "feuilles": [
            "4th period", "3rd period", "2nd period", "1st period",
            "all period", "Time-frame"
        ], # Correspondance aux intervalles d'investissement (5 à 20 ans) [file:1]
        "nombre_total_trimestres": 80, # Pour l'ensemble de la période (1990 T3 à 2010 T2) [file:1],
        "périodes_principales": {
            "nombre": 4,
            "durée_années": 5
        }
    },
    "variables_clés": {
        "concepts_stock_picking": [
            "Large BP",
            "Large ROE",
            "Large SP",
            "Large Return Rate in the last quarter",
            "Large Market Value",
            "Small systematic Risk"
        ], # Pondérations dans chaque ligne [file:1]
        "indicateurs_de_performance": [
            "Annual Return",
            "Excess Return",
            "Systematic Risk",
            "Total Risk",
            "Abs. Win Rate",
            "Rel. Win Rate"
        ], # Mesures quantitatives d'efficacité [file:1]
    },
    "organisation_ligne": {
        "allocation": "distribution pondérale de concepts",
        "mesures": "tous les indicateurs financiers et de risque"
    },
    "chronologie": {
        "debut": "1990 T3",
        "fin": "2010 T2",
        "nombre_périodes": 4,
        "durée_période": "5 ans"
    },
    "analyse_structurée": {
        "effet_des_stratégies": "impact des pondérations différentes sur le rendement et le risque",
        "comparaisons": "entre les concepts dominants et les résultats obtenus",
        "granularité": "possibilité de calculs fins sur chaque ligne et période"
    },
    "synthese_dashboard": {
        "concepts": [
            "Large BP",
            "Large ROE",
            "Large SP",
            "Large Return Rate",
            "Large Market Value",
            "Small systematic Risk"
        ],
        "indicateurs": [
            "Annual Return",
            "Excess Return",
            "Systematic Risk",
            "Total Risk",
            "Abs. Win Rate",
            "Rel. Win Rate"
        ],
        "cadre_temporel": "1990-2010 (20 ans), analyse trimestrielle (80 trimestres)"
    },
    "conclusion": (
        "La base permet une analyse fine du rendement et du risque selon plusieurs "
        "stratégies de stock-picking, sur différents horizons temporels. Les données normalisées "
        "autorisennt des comparaisons détaillées entre méthodes et périodes, offrant une plateforme "
        "idéale pour l'étude multi-dimensionnelle de la performance des portefeuilles."
    ),
    "source": "stock-portfolio-performance-data-set-1.xlsx", # Pour vérification/follow-up [file:1]
    "reference_en_ligne": "https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/128687290/7193f250-57b6-4131-97a0-139df2257ada/stock-portfolio-performance-data-set-1.xlsx"
}

# Affichage exhaustif de la synthèse
for section, contenu in stock_portfolio_dataset.items():
    print(f"{section} : {contenu}")
 # Etapes d'analyse :
 
\documentclass[12pt,a4paper]{article}
\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}
\usepackage[french]{babel}
\usepackage{geometry}
\usepackage{graphicx}
\usepackage{hyperref}
\usepackage{listings}
\usepackage{xcolor}
\usepackage{amsmath}
\geometry{margin=2.5cm}

\definecolor{codebg}{RGB}{245,245,244}
\definecolor{keyword}{RGB}{0,0,180}
\definecolor{string}{RGB}{120,0,0}

\lstset{
  backgroundcolor=\color{codebg},
  basicstyle=\ttfamily\footnotesize,
  keywordstyle=\color{keyword}\bfseries,
  stringstyle=\color{string},
  commentstyle=\itshape\color{gray},
  frame=single,
  breaklines=true,
  tabsize=4,
  showstringspaces=false
}

\begin{document}

\begin{center}
\Huge \textbf{COURS DE SCIENCE DES DONNÉES}\\[0.3cm]
\LARGE \textbf{Analyse Exploratoire d’un Portfolio d’Actions}\\[0.5cm]
\large El Baz Younes\\
\large École Nationale de Commerce et de Gestion (ENCG) – 4ème Année\\[0.3cm]
\hrulefill
\end{center}

\section*{Introduction}

Ce document présente une \textbf{analyse exploratoire des données (EDA)} appliquée à un jeu de données portant sur la performance d’un portefeuille d’actions. 
L’objectif est de comprendre la structure des données, d’en extraire les tendances principales, de détecter les valeurs manquantes et les outliers, et de produire des visualisations pertinentes.

\bigskip
Les outils utilisés incluent \textbf{Python}, les bibliothèques \texttt{pandas}, \texttt{matplotlib}, \texttt{seaborn}, et l’accès à un dataset via \texttt{ucimlrepo}.

\section{Chargement et Préparation des Données}

\subsection*{Installation et Importation des Bibliothèques}

\begin{lstlisting}[language=Python]
pip install ucimlrepo
\end{lstlisting}

\begin{lstlisting}[language=Python]
import pandas as pd
from ucimlrepo import fetch_ucirepo

# Charger le fichier Excel du portefeuille d'actions
excel_file_path = "/content/drive/MyDrive/stock portfolio performance data set.xlsx"
df_excel = pd.read_excel(excel_file_path)

# Afficher les premières lignes
display(df_excel.head())
\end{lstlisting}

\subsection*{Chargement d’un Dataset depuis UCI}

\begin{lstlisting}[language=Python]
# Télécharger le dataset depuis UCI
stock_portfolio_performance = fetch_ucirepo(id=390)

# Extraction des données
X = stock_portfolio_performance.data.features
y = stock_portfolio_performance.data.targets

# Affichage des métadonnées
print(stock_portfolio_performance.metadata)

# Information sur les variables
print(stock_portfolio_performance.variables)
\end{lstlisting}

\section{Analyse Exploratoire des Données}

\subsection{Vue d’Ensemble et Statistiques Descriptives}

Cette étape permet d’obtenir une vision générale du jeu de données :
\begin{itemize}
  \item Types de variables et valeurs non nulles ;
  \item Statistiques descriptives : moyenne, médiane, écart-type, min, max ;
  \item Taille du dataset et structure mémoire.
\end{itemize}

\begin{lstlisting}[language=Python]
# Aperçu du DataFrame
df_excel.info()

# Statistiques descriptives
df_excel.describe()
\end{lstlisting}

\subsection{Analyse des Valeurs Manquantes}

\begin{lstlisting}[language=Python]
# Calcul des valeurs manquantes
missing = df_excel.isnull().sum()
missing_percentage = (missing / len(df_excel)) * 100

# Tableau récapitulatif
pd.DataFrame({
    'Valeurs manquantes': missing,
    'Pourcentage': missing_percentage
})
\end{lstlisting}

\subsection{Visualisation des Distributions}

\begin{lstlisting}[language=Python]
import matplotlib.pyplot as plt
import seaborn as sns

# Histogramme des variables numériques
df_excel.hist(bins=30, figsize=(12, 8), edgecolor='black')
plt.suptitle("Distribution des Variables Numériques")
plt.show()

# Boxplots pour détecter les outliers
plt.figure(figsize=(12,6))
sns.boxplot(data=df_excel, orient="h")
plt.title("Détection des Outliers par Boxplot")
plt.show()
\end{lstlisting}

\subsection{Analyse de Corrélation}

\begin{lstlisting}[language=Python]
# Matrice de corrélation
corr_matrix = df_excel.corr(numeric_only=True)

# Visualisation de la matrice
plt.figure(figsize=(10,8))
sns.heatmap(corr_matrix, annot=True, cmap='coolwarm', center=0)
plt.title("Matrice de Corrélation des Variables Numériques")
plt.show()
\end{lstlisting}

\section{Identification des Outliers}

\begin{lstlisting}[language=Python]
# Méthode de l'IQR
Q1 = df_excel.quantile(0.25)
Q3 = df_excel.quantile(0.75)
IQR = Q3 - Q1

outliers = ((df_excel < (Q1 - 1.5 * IQR)) | (df_excel > (Q3 + 1.5 * IQR)))
outliers.sum()
\end{lstlisting}

Les valeurs extrêmes identifiées par cette méthode doivent être examinées pour déterminer si elles résultent d’erreurs de saisie ou d’événements exceptionnels.

\section{Synthèse et Interprétation}

L’analyse exploratoire a permis de :
\begin{itemize}
  \item Comprendre la structure du dataset et le type de chaque variable ;
  \item Identifier les valeurs manquantes et outliers ;
  \item Observer la distribution des variables et leurs corrélations ;
  \item Détecter des relations entre certaines mesures de performance du portefeuille.
\end{itemize}

Cette EDA constitue la première étape essentielle avant toute modélisation prédictive ou analyse de performance approfondie.

\section*{Conclusion}

Ce travail illustre les fondements pratiques de la \textbf{Science des Données appliquée à la finance}, notamment par l’étude descriptive, la visualisation et l’interprétation des données de performance d’un portefeuille d’actions. 
L’étape suivante consistera à appliquer des modèles d’apprentissage automatique pour prédire ou optimiser les rendements futurs.

\end{document}

