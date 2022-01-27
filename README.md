# Création d'une application ayant pour but l'analyse de la prononciation d'un mot anglais

## Partie scrapping

Une fonction a été développé permettant, à partir d'un dictionnaire anglais, 
de récupérer les liens audios de la prononciation du mot par un britannique et un américain, 
les différentes POS du mot et sa prononciation IPA. <br/>
Concernant cette partie, le premier lien correspond à la prononciation de la première POS par un britanique, le second par un américain, c'est ensuite pour la 2ème POS etc. <br/>
Il en va de même pour la prononciation IPA.

## Manipulation dataframe

A partir du dictionnaire de 1757, j'ai transformé les prononciations par des mots normaux à l'aide d'un dictionnaire de conversion. <br/>
La colonne de prononciation Sampa a été ajouté à l'aide du dictionnaire Bigi. On note cependant que certains mots n'ont pas cette prononciation.
Cela est possiblement du au fait que certains mots ont évolué et ne se retrouve donc plas dans le dictionnaire Bigi. <br/>
On a ensuite effectué la 'traduction' du Sampa vers l'IPA qui est plus couramment utilisée.
Pour diminuer un peu le nombre de valeur manquante, il aurait été possible de rechercher la prononciation IPA sur le dictionnaire
en ligne et effectuer la 'traduction' dans l'autre sens pour avoir la prononciation Sampa.
Cependant certains mots ne trouvent pas non plus dans le dictionnaire en ligne.

## Application

A l'aide de 3 filtres (mot vedette (en regex), prononciation IPA (en regex) et taille maximale) l'utilisateur obtient un tableau ayant
pour nombre de lignes la la plus petite des valeurs entre le nombre de mots respectant les 2 filtres textuels et la taille maximale choisie . Dans ce dernier cas, les mots sont choisis aléatoirement.<br/>
En colonne il y a le mot vedette, le nombre de syllabes, la prononciation d'origine, Sampa et IP. <br/>
Sous ce tableau, on a des players audios des mots sélectionnés pour les prononciations UK et US lorsque le mot a été trouvé sur le dictionnaire en ligne. <br/>
Les fichiers audio sont par ailleurs sauvegardé en local. <br/>
A partir de ces fichiers, j'aurais pu effectuer le spectrogramme des audios mais la librairie librosa n'a pas pu être installée.

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/MerwanCnam/DicoMerwanPetelet/HEAD)<br/>
[Launch Voilà](https://mybinder.org/v2/gh/MerwanCnam/DicoMerwanPetelet/HEAD?urlpath=voila%2Frender%2Fnotebook%2Fmerwan_petelet_App.ipynb)
