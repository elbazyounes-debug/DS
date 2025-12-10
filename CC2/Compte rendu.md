# **Compte Rendu**

## **Analyse du Dataset “MoMA Museum Collection – Artworks & Artists”**

**Date :** 26 Novembre 2025
**Réalisé par :
** Younes ELBAZ
** 22007219
** CAC 2

---

# **Table des Matières**

1. [Introduction et Contexte](#1-introduction-et-contexte)
2. [Chargement & Description des Données](#2-chargement--description-des-données)
3. [Nettoyage et Prétraitement](#3-nettoyage-et-prétraitement)
4. [Analyse Exploratoire (EDA)](#4-analyse-exploratoire-eda)
5. [Analyse Statistique & Corrélations](#5-analyse-statistique--corrélations)
6. [Analyse des Tendances Temporelles](#6-analyse-des-tendances-temporelles)
7. [Exploration des Médiums & Catégories](#7-exploration-des-médiums--catégories)
8. [Modélisation & Approches Prédictives](#8-modélisation--approches-prédictives)
9. [Interprétation & Recommandations](#9-interprétation--recommandations)
10. [Conclusion](#10-conclusion)

---

# **1. Introduction et Contexte**

Le dataset **MoMA Museum Collection** regroupe plus de **150 000 œuvres** du *Museum of Modern Art* (New York).

Il comprend des informations détaillées sur chaque œuvre :

* Titre
* Artiste / Nationalité / Genre
* Année de création
* Date d’acquisition par le musée
* Medium utilisé
* Dimensions
* Type d’œuvre (Print, Painting, Sculpture, Photograph…)

L’objectif de cette analyse est de :

* Comprendre la structure de la collection du MoMA
* Identifier les tendances d’acquisition
* Explorer les médiums les plus représentés
* Analyser les artistes dominants par période
* Comprendre comment les caractéristiques des œuvres évoluent dans le temps

---

# **2. Chargement & Description des Données**

Le dataset est composé de deux fichiers :

### **1. Artworks.csv**

Contient les informations des œuvres :

| Variable               | Description                         |
| ---------------------- | ----------------------------------- |
| Title                  | Nom de l’œuvre                      |
| Artist                 | Nom de l’artiste                    |
| Date                   | Année de création                   |
| Medium                 | Type de médium utilisé              |
| Classification         | Type d’œuvre                        |
| Dimensions             | Dimensions textuelles               |
| DateAcquired           | Date d’entrée au MoMA               |
| AcquisitionYear        | Extraction de l'année d’acquisition |
| Width / Height / Depth | Dimensions nettoyées                |

### **2. Artists.csv**

Contient les informations des artistes :

* Nom
* Genre (Male/Female/Unknown)
* Nationalité
* Année de naissance et décès

---

# **3. Nettoyage et Prétraitement**

Les principales opérations réalisées :

### ✔ **Conversion des dates**

* `Date` → année numérique
* `DateAcquired` → format datetime

### ✔ **Extraction de nouvelles variables**

* `AcquisitionYear`
* `DecadeCreated`
* `ArtistNationality`
* `ArtistGender`

### ✔ **Nettoyage du médium**

Uniformisation des catégories :

* “Gelatin silver print” → Photographie
* “Oil on canvas” → Peinture
* “Lithograph” → Print

### ✔ **Jointure œuvres + artistes**

Sur `ConstituentID`, pour enrichir les données.

### ✔ **Traitement des dimensions**

Extraction automatique des mesures pour analyses futures.

---

# **4. Analyse Exploratoire (EDA)**

### **Distribution des années de création**

* Forte présence d’œuvres du **XXe siècle**, particulièrement entre **1940 et 1980**.
* Rareté d’œuvres antérieures à 1900.

### **Distribution des acquisitions**

Deux périodes majeures d’enrichissement :

* **1940–1960** : expansion de la collection moderne
* **2000–2020** : acquisitions massives d’œuvres contemporaines

### **Artistes les plus présents**

* *Picasso*, *Matisse*, *Andy Warhol*, *Roy Lichtenstein*, *Henri Cartier-Bresson*
  → Ces artistes dominent largement certaines catégories.

---

# **5. Analyse Statistique & Corrélations**

### Variables corrélées :

* **Année de création & année d’acquisition** :
  → corrélation positive, les œuvres récentes sont acquises plus tôt.

* **Medium & dimensions** :
  → certaines catégories comme *sculpture* ont des dimensions plus grandes.

### Peu de corrélation globale

Comme attendu dans un dataset artistique, beaucoup de variables sont **catégorielles** ou **qualitatives**, rendant les corrélations faibles mais informatives.

---

# **6. Analyse des Tendances Temporelles**

### **1. Nombre d’acquisitions par année**

* Pic important dans les années **1950**
* Nouvelle hausse après **2000**

### **2. Âge moyen des œuvres au moment de l’acquisition**

* Avant 1950 : on acquiert des œuvres très anciennes
* Après 2000 : acquisitions d’œuvres plus récentes (contemporaines)

### **3. Évolution des médiums**

* Photographie : explosion après les années **1970**
* Peinture : stable mais moins dominante
* Sculpture : croissance modérée
* Prints & multiples : très représentés

---

# **7. Exploration des Médiums & Catégories**

### **Classement des médiums les plus utilisés :**

1. **Photography**
2. **Print**
3. **Illustrated Book**
4. **Painting**
5. **Drawing**

### Observations :

* Le MoMA possède une proportion **énorme** de photographies.
* Les peintures représentent une minorité mais sont parmi les œuvres les plus iconiques.
* Les illustrations & prints dominent numériquement car souvent acquis en séries.

---

# **8. Modélisation & Approches Prédictives**

Bien que le dataset soit principalement descriptif, certains objectifs prédictifs sont pertinents :

### **Objectif choisi : prédire l’âge à l’acquisition**

**AgeAtAcquisition = AcquisitionYear – YearCreated**

### **Algorithmes testés :**

* Régression Linéaire
* Ridge Regression
* Random Forest Regressor

### **Features utilisées :**

* Medium
* Classification
* Dimensions
* Nationalité de l’artiste
* Genre de l’artiste

### Résultats :

* La régression linéaire explique peu la variance (car dataset très hétérogène).
* Random Forest offre les meilleures performances, confirmant :

  * forte importance du médium
  * influence modérée de la nationalité et de l’année de création

---

# **9. Interprétation & Recommandations**

### **Ce que révèle l’analyse :**

* La collection est très riche en **photographies et prints**.
* Les artistes modernes du XXe siècle dominent numériquement.
* Les acquisitions suivent des politiques évolutives selon les décennies.
* Les caractéristiques des œuvres n’expliquent pas toujours bien l’âge à l’acquisition → dataset très artistique, non linéaire.

### **Recommandations pour aller plus loin :**

1. Analyser les artistes sous-représentés (female artists, nationalités émergentes)
2. Étudier les réseaux artistiques (graphes artistes–médiums)
3. Développer un modèle de classification des médiums
4. Mesurer l'évolution de la diversité artistique du MoMA
5. Étudier comment la collection reflète l’évolution de l’art moderne et contemporain

---

# **10. Conclusion**

Cette étude du dataset du **MoMA Museum Collection** montre :

✔ Une collection immense et diversifiée
✔ Une forte orientation vers la photographie et les impressions
✔ Des dynamiques d’acquisition liées aux périodes historiques
✔ Une richesse analytique exploitant artistes, médiums, dimensions et dates
✔ Des possibilités de modélisations avancées malgré la nature artistique des données

L’analyse constitue une **base solide** pour aller plus loin dans la compréhension de l’évolution artistique du MoMA.

