# Bienvenue sur la documentation de Glosaurus

## Le projet

Nous développons une application de bureau de type **"Linter de Glossaire Intelligent"**.  
L'objectif est de faciliter l'écriture des termes métier dans le code, pour qu'il corresponde mieux au contexte métier.

Notre outil vise à résoudre ce problème en offrant :

1.  Un **Gestionnaire de Glossaire** centralisé.

2.  Une **Assistance IA** pour enrichir ce vocabulaire.

3.  Un **Vérificateur de Code** (Linter) pour garantir le respect des termes définis.

## Fonctionnalités principales

### Gestionnaire de Glossaire
Une interface complète pour créer, modifier, importer et exporter vos dictionnaires de données.

### Intelligence artificielle locale (privée)
Nous avons intégré un moteur d'IA léger mais performant permettant le fonctionnement **entièrement hors-ligne** (pas de fuite de données). Son **rôle** est de suggérer des synonymes, antonymes et contextes pour chaque mot ajouté.

### Analyseur de code (parser)
Le cœur de la vérification.

*   **Fonctionnement :** L'utilisateur importe ses fichiers sources.

*   **Analyse :** Le système scanne le code (variables, fonctions, classes) et le compare au glossaire.

*   **Rapport :** Il signale les termes inconnus ou propose des corrections basées sur le glossaire officiel.

## Contenu de cette documentation

Ce site a pour vocation de présenter notre **démarche de Recherche et Développement**. Vous y découvrirez :

*   **Les Recherches IA :** Nos tests sur différents modèles (Word2Vec, BERT...), nos comparatifs de performances et la justification de nos choix finaux.
*   **L'Architecture du Parser :** Comment nous transformons du code brut en données analysables (AST, Tokenization).
*   **Les Choix Techniques :** Front-end, Back-end, et intégration des composants.

---
*Projet réalisé dans le cadre de la SAE de 3ème année de BUT Informatique - IUT du Limousin.*