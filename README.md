#### IN ENLIGSH 🇬🇧 
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

:pushpin: **Divide** the csv table into two parts: keep part of the session data and pivot the second part of the questions.

:pushpin: **Convert** the titles according to the question id and name the options and responses columns.

:pushpin: **Organise** the columns so that you have the options followed by their responses for each question.

:pushpin: **Distinguish** between free input columns.

:pushpin: **Create values label meta** for multiple option questions.

:pushpin: **Rename** single choice of multiple option questions.

:pushpin: **Create labels meta** for all columns.

:pushpin: **Create measures meta** for all columns.

:pushpin: **Fill in the missings meta** with -1 for questions with multiple options and free numeric fields.

## csv source
This is an example of a [csv file](https://github.com/LisaKey/convert_csv_to_sav/blob/main/response.csv) exported from the form.

## sav result
This is the [sav file](https://github.com/LisaKey/convert_csv_to_sav/blob/main/response.sav) we want to have after transformations.

## Details about the csv content
we have two parts of data in the .csv file
#### :point_right: :point_right: **firt part** Session or form information : 
- :pushpin: `session_id` : a unique identifier with numeric type, used as the form identifier.
- :pushpin: `localisation` (longitude) : with numeric type that is automatically recorded and with echelle measure like all numeric type.
- :pushpin: the `comment` : with chaine type and nominal measure similar others sting in sav file.
- :pushpin: `date` : with date type and ordinal measure.
#### :point_right: :point_right: **second part** Diffrent type of questions :
- :pushpin: `multiple option with a single choice` : examples Q_1 or Q_3, These are numeric type because option_index is an integer, and we generate value labels using the option_index.
- :pushpin: `simple numeric` : example Q_2, this type is numeric since users input an integer. It is identified when option_index is empty.
- :pushpin: `simple chaine` : Also identified by an empty option_index
   - simple input : example Q_5 is a basic text input in the form
   - reorderer list : example Q_7 considered as a chaine but but it requires users to reorder elements in the form.
- :pushpin: `multiple option with multiple choice` : with ordinal measure
   - simple question : example Q_4 with type contains multiple options with an "O" in the column name. The last option is "Others", considered as a string (like Q_5).
   - grid question : example Q_6 with type has a grid structure, allowing multiple choices. It is numeric and does not include an "Others" field.
### Note :
- The answer column helps indicate if the option was selected (1) or not (NaN).
- We use -1 for all messing values of numeric questions.
### Next step :
we will develop an additional column to distinguish mesure between ordinal and norminal measure for multiple-choice and single-choice questions. This will be implemented when the admin inserts the questions in the forme before the client provides answers.


#### EN FRANCAIS 🇫🇷
# Convertir un fichier .csv en un fichier .sav avec python :snake :
Nous avons utilisé python :snake : pour convertir un fichier csv en un fichier sav avec toutes les modifications nécessaires pour l'ouvrir dans spss de IBM et pouvoir analyser nos données.

## Introduction
Nous disposons de données exportées d'un formulaire concernant les opinions de clients sur leur consommation de certaines marques. Ces données contiennent des informations sur la session telles que sa date, sa localisation géographique ou un commentaire et nous avons d'une autre part des informations (réponses des clients) pour des questions avec plusieurs options de réponse à choix multiples et également à choix unique comme aussi des réponses de champs de saisie libres avec données numériques ou texte.

## Ce dont nous avons besoin
Les bibliothèques :books: utilisées sont :

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

## Détail du contenu du fichier CSV
Nous avons deux parties dans notre fichier.
#### :point_right: **première partie** Informations de la session ou du formulaire enregitré : 
##### :round_pushpin: session_id : identifiant unique de type numérique, comme l'identifiant du formulaire enregitré.
##### :round_pushpin: localisation (longitude) : de type numéric et enregistrée automatiquement, de mesure echelle comme la plus part des champs de types numériques.
##### :round_pushpin: comment : de type chaine et de mesure nominal comme la plus part des champs chaine.
##### :round_pushpin: date : de type date et de mesure ordinal.
#### :point_right: **deuxième partie** Type de questions :
##### :round_pushpin: multiple option avec choix unique : comme Q_1 or Q_3, de type numérique, car option_index est un entier et permet de générer des value labels.
##### :round_pushpin: simple numéric : comme Q_2, de type numérique car le client saisit un entier dans l'input, on le reconnait quand option_index est vide.
##### :round_pushpin: simple chaine : on le distinque aussi quand option_index est vide.
   - simple input : comme Q_5 un simple champ sting du formulaire.
   - reorderer list : comme Q_7 est considéré comme chaine mais le client doit ordonner des éléments sur le formulaire.
##### :round_pushpin: multiple option avec multiple choix : de mesure ordinal
   - simple question : comme Q_4 contient multiple options avec un O sur le noms des colonnes, son type est numérique et la dernière option est 'Autres' de type chaine.
   - grid question : comme Q_6 est une grille ou le client choisit plusieurs options aussi, de type numérique et sans champs 'Autres'.
### Note : 
La colonne answer nous permet de savoir si l'option a été choisie (1) ou non (NaN).
Nous mettons -1 pour toutes les valeurs manquantes des questions de type numérique.
### Prochaine étape :
Nous allons développé une colonne spécifique pour distinguer les mesures norminal et ordinal pour les questions à choix unique et choix multiple, l'administrateur l'insèrera avec les questions avant de transmettre au client.

