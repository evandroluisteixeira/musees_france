# Analyse avancée des Musées de France  
Cartographie interactive, typologies et enrichissement visuel

## Présentation

Ce projet propose une analyse avancée des musées de France à partir de données publiques, en combinant :

- analyse exploratoire des données  
- visualisations statistiques  
- cartographie interactive avec Folium  
- enrichissement visuel via l’API Wikimedia Commons  

L’objectif est de montrer comment la science des données peut être mobilisée pour comprendre le paysage culturel français, tout en produisant un notebook didactique, réutilisable et adapté à un portfolio.

---

## Objectifs du projet

- Explorer la répartition territoriale des musées en France  
- Analyser les typologies de musées à partir de leur nom officiel  
- Visualiser les musées sur une carte interactive avec clusters  
- Enrichir les données avec informations de contact et images  
- Produire une table finale exploitable pour un tableau de bord ou un site web

---

## Données

- **Fichier :** `musees-de-france.csv`  
- **Source :** Base « Musées de France » (Ministère de la Culture, données ouvertes)  
- **Format :** CSV, séparateur `;`  
- **Champs principaux :**  
  - `Identifiant Muséofile`  
  - `Région administrative`  
  - `Département`  
  - `Commune`  
  - `Nom officiel du musée`  
  - `Adresse`  
  - `Code Postal`  
  - `Téléphone`  
  - `URL`  
  - `Latitude`, `Longitude`  

Le fichier doit être importé manuellement dans Google Colab avant exécution du notebook.

---

## Contenu du notebook

1. **Importation des bibliothèques**  
   `pandas`, `seaborn`, `matplotlib`, `folium`, `requests`, etc.

2. **Chargement des données**  
   - Import du fichier `musees-de-france.csv`  
   - Aperçu des premières lignes

3. **Aperçu général**  
   - `df.info()`  
   - `df.describe(include="all")`  
   - Vérification des valeurs manquantes

4. **Nettoyage et préparation**  
   - Suppression des doublons  
   - Normalisation des noms de régions  
   - Conversion des départements en chaînes de caractères

5. **Analyse par région**  
   - Histogramme du nombre de musées par région

6. **Classification thématique automatique**  
   - Création d’une variable `Type de musée` à partir du nom officiel  
   - Visualisation des catégories les plus représentées

7. **Analyse par département**  
   - Histogramme horizontal de la répartition des musées par département

8. **Carte interactive (Folium + MarkerCluster)**  
   - Centrage de la carte sur la moyenne des coordonnées  
   - Ajout de marqueurs avec :  
     - nom du musée  
     - commune et département  
     - lien vers le site officiel

9. **Enrichissement visuel (API Wikimedia Commons)**  
   - Requête à l’API pour récupérer une image libre associée au nom du musée  
   - Ajout d’une colonne `Image` contenant l’URL de la vignette

10. **Tableau enrichi**  
    - Sélection des colonnes :  
      `Nom officiel du musée`, `Commune`, `Département`, `Téléphone`, `URL`, `Image`  
    - Génération d’un tableau HTML avec affichage des images

11. **Conclusion**  
    - Synthèse des résultats  
    - Pistes d’extension (tableau de bord, analyses locales, croisement avec d’autres données)

---

## Technologies utilisées

- **Langage :** Python 3  
- **Analyse et manipulation :**  
  - `pandas`  
  - `seaborn`  
  - `matplotlib`  
- **Cartographie :**  
  - `folium`  
  - `folium.plugins.MarkerCluster`  
- **Requêtes web :**  
  - `requests` (API Wikimedia Commons)  
- **Environnement :**  
  - Google Colab  

---

## Résultats principaux

- Visualisation claire de la répartition des musées par région et département  
- Typologie automatique des musées à partir de leur nom  
- Carte interactive de France avec clusters de musées  
- Tableau enrichi combinant :  
  - informations de contact  
  - liens vers les sites officiels  
  - images issues de Wikimedia Commons  

Ce projet illustre comment articuler données ouvertes, outils de data science et ressources du web pour produire une lecture riche du paysage culturel.

---

## Pistes pour aller plus loin

- Focalisation sur une région spécifique (par exemple, Normandie)  
- Création d’une carte interactive thématique (par type de musée)  
- Intégration dans un tableau de bord (Plotly Dash, Streamlit)  
- Croisement avec d’autres bases (monuments historiques, fréquentation, données socio-démographiques)  

---

## Auteur

**Evandro Luis Teixeira**  
Profil hybride à l’intersection de la culture, de la pédagogie et des technologies numériques.  
Ce projet s’inscrit dans un portfolio de data science appliquée aux secteurs culturels et territoriaux.

---

## Licence

Ce projet est publié sous licence MIT.  
Vous êtes libre de l’utiliser, le modifier et le partager avec attribution.
