# directional-logging

## Introduction
Les fonctions de traitement des données d'abattage directionnel se présentent sous la forme de scripts Python pour la boîte à outils Traitements de QGIS (voir http://docs.qgis.org/2.8/en/docs/user_manual/processing/scripts.html).

## Installation
Déposer les fichiers dans le répertoire ~/.qgis2/processing/scripts (ou C:\Users\You\\.qgis2\processing\scripts sous Windows).

## Données d'entrée

### Relevés terrain

- Charger le shapefile 'Pointage directionnel abattage' (en système géographique, "WGS 84").
- Activer l'édition de la couche, ouvrir la table attributaire et s'assurer que l'attribut 'Name' correspond au motif suivant :
"Une suite de chiffre, ou, une suite de chiffres suivie d'une suite de lettres majuscules".

Un relevé dont l'attribut 'name' ne correspondrait pas à ce motif ne serait pas traîté ou générerait une erreur.

N.B. : Le format original des relevés (le GPX) contient un champ 'cmt' ("commentaire") où peuvent être enregistrées des informations complémentaires (https://fr.wikipedia.org/wiki/GPX_%28format_de_fichier%29#Structure).
Lesquelles, stockées dans le champ 'name', empêcheraient la reconnaissance du motif. (Voir champ "Note" dans l'interface d'enregistrement de waypoint de l'interface du Garmin 62s)

Quitter le mode édition en enregistrant les éventuelles corrections d'attributs.

### Diamètre

- Ouvrir avec MS Exel le tableau de désignation.
- Repérer la feuille contenant la correspondance numéro-diamètre et l'exporter au format CSV (https://fr.wikipedia.org/wiki/Comma-separated_values).
- Charger le fichier dans QGIS ("Ajouter une couche de texte délimité") en s'assurant que "Pas de géométrie (juste la table)" est sélectionné comme 'Définition de la géométrie'.
