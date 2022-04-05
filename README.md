
# Idée de base

Créer un dashboard Python/Plotly où quelqu'un peut uploader ses relevés ENEDIS horaires, ainsi que les données Météo du point le plus proche.


Allez sur https://mon-compte-particulier.enedis.fr/
Onglet "Suivre mes mesures"
Télécharger le csv des données horaires depuis le plus longtemps que vous pouvez.

Pour exporter un notebook en page html sans le code python:
```bash
jupyter nbconvert --no-input --to html notebook.ipynb
```

# To do

- ajouter columns year, month, season, dayofweek, etc
- utiliser du ML basique pour remplir les points manquants
- ajouter la variable thermostat cible : 20 la journée, 18 la nuit (0h:6h). Possibilité de tester sur une période (e.g. une semaine) et ensuite faire un script qui calcule combien on a gagné, et donc combien on gagnerait en utilisant toute l'année cette nouvelle température cible.
- faire les plots de base
- recupérer les données de Météo France automatiquement à partir d'une adresse
- faire des plots de corrélation entre météo et conso
- analyse en composante
- intégrer estimation de production des panneaux solaires
- ajouter une date précise d'ajout d'un nouvelle équipement (isolation comble renforcée) pour ensuite comparer avant/après sur conditions équivalentes. Prendre un groupe de jour




1er novembre 2020, Enedis a commencé à faire des relevés "horaires" toutes les demi-heures. C'est cool mais ça fout le bordel. Aucune idée de si c'est pareil pour tout le monde ou juste relié à mon compteur.



# Installation

```bash
conda create -n elec python=3.8
conda activate elec
```

```bash
conda install -c conda-forge jupyterlab
pip install pandas matplotlib seaborn scikit-learn streamlit
```

# Récupérer les données

##

## Historique météo

J'aurais préféré le faire avec une API
https://data.toulouse-metropole.fr/explore/dataset/11-station-meteo-toulouse-soupetard/information/


# Visualisations

Courbe de charge sur une journée, avec groupe par saison ? par mois ? couleur de chaque courbe égale à la température moyenne du jour puis possibilité de faire des groupes en fonction

# Analyse

Analyse en composante (indépendante) pour isoler :
- chauffage
- chauffe-eau
- plaque cuisson et four

Baseline :
- box internet (sauf si éteinte la nuit)
- appareils en veille
- ??

Introduire une composante panneau solaire, avec leur contribution théorique selon les heures à la réduction de la courbe de charge de conso.

# Publier une version interactive : streamlit

- https://share.streamlit.io/daniellewisdl/streamlit-cheat-sheet/app.py
- https://rcsmit.medium.com/making-interactive-webbased-graphs-with-python-and-streamlit-a9fecf58dd4d
- https://streamlit.io/gallery?category=data-visualization
- https://docs.streamlit.io/
- Example with file uploading: https://share.streamlit.io/baligoyem/dataqtor/main/home.py


# Références

- https://towardsdatascience.com/time-series-analysis-using-pandas-in-python-f726d87a97d8
- package a tester pour la gestion des dates https://github.com/arrow-py/arrow




