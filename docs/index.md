# Bienvenue sur notre site de recherches

## Le projet :
Nous travaillons sur un outil permettant de suggérer intelligement des termes métiers pour améliorer la qualité de nommage des variables. Pour le moment nous développons une application de glossaire métier, que nous voudrions enrichir avec des suggestions. Et par la suite le but serait d'ajouter la suggestion intelligente directement dans notre IDE.

Pour cela nous souhaitons utiliser les notions d'embedding et l'utilisation des vecteurs pour trouver des mots comme avec l'exemple `roi - homme + femme = reine`.

Ce site va donc nous permettre d'accueillir nos résultats de recherches qui ont pour but de trouver le meilleur outil et le plus adéquat pour trouver des suggestions de mots en fonction du contexte sémantique que l'on a.

## Les recherches :

Durant nos recherches, nous allons nous renseigner et tester différents modèles d'embedding, comme Word2Vec, BERT et tester des modèles IA qui utilise ces différents embedding. Nous comparerons les résultats des mots rendu, voir si on peut faire des "opérations entre les vecteurs" comme dans l'exemple `roi - homme + femme = reine`, si c'est possible par exemple d'ajouter le vecteur `synonyme` a un mot pour en trouver les différents synonyme (Ex : `beau + synonyme : magnifique`). Comparer les vitesse d'utilisation de ces différents modèles et faire des statistiques et comparatifs afin de déterminer le plus pertinent pour notre projet.