# Projet-2AS1
**Consignes de lecture**
#
Arborescence fichiers:<br>


- Traitement de données:

      *-fichier : description*<br>
          *> output*
    
    - [trait_liste_manuelle](trait_liste_manuelle.ipynb) : traitement d'une liste de mouvements et d'auteurs [liste_auteurs_manuelle.csv](liste_auteurs_manuelle.csv) afin de créer un dataset propre.
        > Création [auteurs_man.csv](auteurs_man.csv)
    - [sub_scrap](sub_scrap.ipynb) : scraping de cette [page](https://fr.wikipedia.org/wiki/Cat%C3%A9gorie:%C3%89crivain_par_mouvement_ou_courant_litt%C3%A9raire) afin d'obtenir des mouvements littéraires. Le dataset créé sera complété par [auteurs_man.csv](auteurs_man.csv)-après traitement- afin d'augmenter la quantité de données.
        > Création [data.csv](data.csv)
    - [mvm_scrap](mvm_scrap.ipynb) : scraping de cette [page](https://fr.wikipedia.org/wiki/Liste_des_mouvements_litt%C3%A9raires) afin d'obtenir une liste de mouvements littéraires puis scraping de chaque page de chaque mouvement.
        > Création [mouvements_wiki_cleaned.csv](Mouvements_wiki_cleaned.csv) 
    - [cleaning_mouvements](cleaning_mouvements.ipynb) : 
        > Création [auteurs_completed.csv](auteurs_completed.ipynb) à partir de [data.csv](data.ipynb) : on rajoute la page wikipedia dans son ensemble si possible.<br>
        > Création [Mouvements_wiki_cleaned1.csv](Mouvements_wiki_cleaned1.csv) à partir de [Mouvements_wiki_cleaned.csv](Mouvements_wiki_cleaned.csv) : différence au niveau du format des noms des mouvements (format % ou texte classique).<br>
- Modélisation:
    - Classification:
        > [Dictionary method](pred_dictionary_method.ipynb) : prédiction du mouvement auquel appartient un auteur sur la base du comptage. On compare de différentes manières le texte de la page wikipédia de chaque auteur, ou simplement le résumé, avec les informations obtenues sur chaque mouvement littéraire via leur page wikipédia afin de prédire de laquelle il est le plus proche.<br>
        > [Body](body.ipynb) : on teste simplement quelques modèles connus mais sans pousser par manque de temps.
    - Clustering: 
        > [LDA](LDA.ipynb) : utilisation de ce topic model pour tenter d'agréger les corpus de textes que sont les pages wikipédia des auteurs en cluster correspondant aux mouvements littéraires.
- Visualisation:
    - [Word clouds](projet_python_visualisation(1).ipynb) : nettoyage, simplification et lemmatisation des textes contenus dans les pages wikipédia des mouvements littéraires pour les afficher dans des wordclouds contenant 50 mots. Cela permet de faire ressortir les termes les plus importants. Cette visualisation est en quelque sorte le pendant qualitatif des dictionary methods.
