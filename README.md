# Projet-2AS1

**Esprit et but du projet** 

L'objectif de ce projet était d'utiliser les données disponibles sur wikipédia pour associer à des auteurs le mouvement littéraire auquel ils appartiennent en utilisant des méthodes d'analyse de texte/NLP. Nous nous sommes donc tournés vers des techniques de classification/topic modeling pour essayer de reconstituer ces mouvements. Bien que les tâches et les techniques soient classiques, les notions que nous essayons de capturer sont complexes et assez abstraites, donnant son intérêt au sujet.
Nous avons été amené à scraper des pages wikipédia afin d'obtenir des listes de mouvement et d'auteurs automatiquement et manuellement pour compléter lorsque nécessaire. 
Nous avons également transformer ces données textuelles pour mieux les interpréter et les visualiser, avant de passer aux différentes modélisations. 

Vous trouverez ci-dessous le détail des fichiers de code et .csv produits et les tâches auxquels ils correspondent.

**Consignes de lecture**
#
Arborescence fichiers:<br>

<sub><sup>*-fichier : description*</sup></sub><br>
     <sub><sup>*> output*</sup></sub>

- Traitement de données:
    - [trait_liste_manuelle](trait_liste_manuelle.ipynb) : traitement d'une liste de mouvements et d'auteurs [liste_auteurs_manuelle.csv](liste_auteurs_manuelle.csv) afin de créer un dataset propre.
        > Création [auteurs_man.csv](auteurs_man.csv)
    - [sub_scrap](sub_scrap.ipynb) : scraping de cette [page](https://fr.wikipedia.org/wiki/Cat%C3%A9gorie:%C3%89crivain_par_mouvement_ou_courant_litt%C3%A9raire) afin d'obtenir des mouvements littéraires. Le dataset créé sera complété par [auteurs_man.csv](auteurs_man.csv)-après traitement- afin d'augmenter la quantité de données.
        > Création [data.csv](data.csv)
    - [mvm_scrap](mvm_scrap.ipynb) : scraping de cette [page](https://fr.wikipedia.org/wiki/Liste_des_mouvements_litt%C3%A9raires) afin d'obtenir une liste de mouvements littéraires puis scraping de chaque page de chaque mouvement.
        > Création [mouvements_wiki_cleaned.csv](Mouvements_wiki_cleaned.csv) 
    - [cleaning_mouvements](cleaning_mouvements.ipynb) :
        > Création [auteur_incomplete_completed.csv], [auteurs_completed_lem.csv], [auteurs_complete2.csv] : rajouter de données wikipedia via la bibliothèque Wikipédia pour des auteurs pour lesquels une partie du scraping précédent avait échoué.
        > Création [auteurs_completed.csv](auteurs_completed.ipynb) à partir de [data.csv](data.ipynb) : on rajoute la page wikipedia dans son ensemble si possible.<br>
        > Création [Mouvements_wiki_cleaned1.csv](Mouvements_wiki_cleaned1.csv) à partir de [Mouvements_wiki_cleaned.csv](Mouvements_wiki_cleaned.csv) : différence au niveau du format des noms des mouvements (format % ou texte classique).<br>
- Modélisation:
    - Classification:
        > [Dictionary method](pred_dictionary_method.ipynb) : prédiction du mouvement auquel appartient un auteur sur la base du comptage. On compare de différentes manières le texte de la page wikipédia de chaque auteur, ou simplement le résumé, avec les informations obtenues sur chaque mouvement littéraire via leur page wikipédia afin de prédire de laquelle il est le plus proche.<br>
                > Création [auteurs_pred_1.csv] : résultat des prédictions avec dictionary method sur data.csv
                > Création [auteurs_pred2.csv] : résultat des prédictions avec dictionary method les auteurs de data.csv pour lesquels les données des mouvements associées ont bien été récupéres. Cela représente une perte de quelques dizaines d'entrées par rapport à auteurs_pred_1. C'est sur ce dataframe que sont évaluées les méthodes de dictionnaire.
        > [Body](body.ipynb) : on teste simplement quelques modèles connus mais sans pousser par manque de temps.
    - Clustering: 
        > [LDA](LDA.ipynb) : utilisation de ce topic model pour tenter d'agréger les corpus de textes que sont les pages wikipédia des auteurs en cluster correspondant aux mouvements littéraires.
- Visualisation:
    - [Word clouds](projet_python_visualisation(1).ipynb) : nettoyage, simplification et lemmatisation des textes contenus dans les pages wikipédia des mouvements littéraires pour les afficher dans des wordclouds contenant 50 mots. Cela permet de faire ressortir les termes les plus importants. Cette visualisation est en quelque sorte le pendant qualitatif des dictionary methods.
