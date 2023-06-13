# Manipulation et visualisation de données géographiques

Pour s'initier à la manipulation de données géographiques, j'ai construis deux notebooks à partir de données en accès libre : 
- viz_AirpdLoire.ipynb se base sur les données d'Air Pays de la Loire traitant de la qualité de l'air dans le département Loire-Atlantique
- analyse.ipynb récupère les données de la base [MeteoNet](https://meteonet.umr-cnrm.fr/) et celles de l'INSEE via la librairie [pynsee](https://readthedocs.org/projects/pynsee/)
#
requirements.txt inclus les librairies python nécessaire à l'environnement pour réproduire les résultats des deux notebooks. 
#
Données accessibles concerant la qualité de l'air : 
- ApdL = par heure sur les 11 stations, plusieurs polluants disponible
- SYNOP = historique des relevés météo de France (1 station a Bouguenais : pression, variation de pression, direction et vitesse du vent, T°, humidité...). Relevé toutes les 3h. https://public.opendatasoft.com/explore/dataset/donnees-synop-essentielles-omm/table/?flg=fr&sort=date&refine.nom_dept=Loire-Atlantique&refine.date=2023
- MeteoFrance = modélisation fine sur toute la france, mais soumis a redevance. https://donneespubliques.meteofrance.fr/?fond=produit&id_produit=131&id_rubrique=51
- jeu de données MeteoNet = relevés sur 3 ans (2016-2018) dans la zone nord ouest (Nantes inclus). 218Gb mais divisble selon interet. https://meteonet.umr-cnrm.fr/




## viz_AirpdLoire.ipynb

Notebook pour la visualisation des mesures d'Air Pays de la Loire sur la Loire-atlantique en PM10 sur une semaine (19/03/22023 au 25/03/2023) avec un pas d'1h. Il inclus la récupération des données, le pré-processing de filtrage, line plot des valeurs sur une journée, ainsi que la localisation sur fond de carte des stations de mesure.

Le fichier PM10_horaire_semaine.csv est issu de la base de mesure. Il est intégrer à ce git pour facilité l'utilisation du notebook. 



## analyse.ipynb

Notebook de manipulation des données MeteoNet. Focalisation sur la zone Nord-Ouest et l'année 2018. Cela inclus le filtrage de pré-processing (on ne s'interesse pour l'instant qu'à la localisation), la visualisation des positions des stations, ainsi que la sélection des stations situées en Loire Atlantique. Le CSV est absent de ce git car trop volumineux.

Cela a aussi été l'occasion de prendre en main l'API de l'INSEE pour récuperer les limites administratives des departements autour de la Loire-Atlantique. A partir de cela j'ai affiché les station météo et les station Air Pays de la Loire sur ce fond de carte. 
