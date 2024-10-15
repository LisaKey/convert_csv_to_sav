#### IN ENLIGSH
# Convert .csv file to .sav file with python :snake:
We used python :snake: to convert a csv file into a sav file with all the modifications needed to open it in IBM spss and be able to analyse our data.

## Introduction
We have data exported from a form concerning customer opinions on their consumption of a certain brand. This data contains information of the session like its date,a geographical position or comment and we also have another information like answers of the customers for questions with several options of answers with multiple choice and also with single choice, it also has free input fields to provide numeric or text content.

## what we need
The libraries :books: used are:
:pushpin: `pandas`  
:pushpin: `pyreadstat`  
:pushpin: `sys`  
:pushpin: `chardet`  
:pushpin: `os`

## what we have to do
we carried out a major transformation on the csv file to obtain a suitable soap for analysing the data on the IBM spss

### Transformation steps :
:pushpin: **Divide** the csv table into two parts: keep part of the session data and pivot the second part of the questions
:pushpin: **Convert** the titles according to the question id and name the options and responses columns
:pushpin: **Organise** the columns so that you have the options followed by their responses for each question
:pushpin: **Distinguish** between free input columns
:pushpin: **Create values label meta** for multiple option questions
:pushpin: **Rename** single choice of multiple option questions
:pushpin: **Create labels meta** for all columns.
:pushpin: **Create measures meta** for all columns.
:pushpin: Fill in the missings meta with -1 for questions with multiple options and free numeric fields

## csv source
This is an example of a [csv file](https://github.com/LisaKey/convert_csv_to_sav/blob/main/response.csv) exported from the form.

## sav result
This is the [sav file](https://github.com/LisaKey/convert_csv_to_sav/blob/main/response.sav) we want to have after transformations.


#### EN FRANCAIS
# Convertir un fichier .csv en un fichier .sav avec python :snake :
Nous avons utilisé python :snake : pour convertir un fichier csv en un fichier sav avec toutes les modifications nécessaires pour l'ouvrir dans spss de IBM et pouvoir analyser nos données.

## Introduction
Nous disposons de données exportées d'un formulaire concernant les opinions de clients sur leur consommation de certaines marques. Ces données contiennent des informations sur la session telles que sa date, sa localisation géographique ou un commentaire et nous avons d'une autre part des informations (réponses des clients) pour des questions avec plusieurs options de réponse à choix multiples et également à choix unique comme aussi des réponses de champs de saisie libres avec données numériques ou texte.

## Ce dont nous avons besoin
Les bibliothèques :books : utilisées sont :
:pushpin: `pandas`  
:pushpin: `pyreadstat`  
:pushpin: `sys`  
:pushpin: `chardet`  
:pushpin: `os`

## Ce que nous avons à faire
nous avons effectué une transformation majeure du fichier csv pour obtenir un sav adapté à l'analyse des données sur spss de IBM.

### Les étapes de la transformation :
:pushpin: **Diviser** le tableau csv en deux parties : garder une partie des données de session et pivoter la seconde partie des questions.
:pushpin: **Convertir** les titres en fonction de l'id question et nommer les colonnes options et responses.
:pushpin: **Organiser** les colonnes de manière à avoir les options suivies de leurs responses pour chaque id question.
:pushpin: **Distinguer** les colonnes à entrée libre, numérique ou chaine.
:pushpin: **Créer les libellés des valeurs** pour les questions à options multiples.
:pushpin: **Renommer** les questions à choix unique.
:pushpin: **Remplir les libellés** des colonnes.
:pushpin: **Créer les méta données des mesures** pour les différents types de columns.
:pushpin: **Remplir les méta données des manquants** avec -1 pour les questions à options multiples et les champs numériques

## Fichier source .csv
Ceci est un exemple de [fichier csv](https://github.com/LisaKey/convert_csv_to_sav/blob/main/response.csv) que nous avons exporté de notre formulaire.

## Le résultat du fichier .sav
Ceci est le [fichier sav](https://github.com/LisaKey/convert_csv_to_sav/blob/main/response.sav) que nous souhaitons avoir après les transformations.
