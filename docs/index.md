# Bienvenue sur la documentation de Glosaurus

## Le projet

Nous développons une application desktop de type **"Linter de Glossaire Intelligent"**.  
Notre constat est simple : la qualité du code passe avant tout par la clarté des termes utilisés. Lorsqu'un développeur utilise un mot vague ou incorrect à la place d'un terme métier précis, la dette technique augmente.

Notre outil vise à résoudre ce problème en offrant :

1.  Un **Gestionnaire de Glossaire** centralisé.

2.  Une **Assistance IA** pour enrichir ce vocabulaire.

3.  Un **Vérificateur de Code** (Linter) pour garantir le respect des termes définis.

## Fonctionnalités Principales

### Gestionnaire de Glossaire
Une interface complète pour créer, modifier, importer et exporter vos dictionnaires de données. C'est la source de vérité de votre projet.

### Intelligence Artificielle Locale (Privée)
Nous avons intégré un moteur d'IA léger mais puissant, fonctionnant **entièrement hors-ligne** (pas de fuite de données).

*   **Rôle :** Suggérer des synonymes, antonymes et contextes pour chaque mot ajouté.

*   **Technologie :** Utilisation d'embeddings (vecteurs de mots) pour comprendre le sens et non juste l'orthographe (ex: comprendre que `Client` est proche de `Utilisateur`).

### Analyseur de Code (Parser)
Le cœur de la vérification.

*   **Fonctionnement :** L'utilisateur importe ses fichiers sources.

*   **Analyse :** Le système scanne le code (variables, fonctions, classes) et le compare au glossaire.

*   **Rapport :** Il signale les termes inconnus ou propose des corrections basées sur le glossaire officiel.

## Contenu de cette documentation

Ce site a pour vocation de présenter notre **démarche de Recherche & Développement**. Vous y découvrirez :

*   **Les Recherches IA :** Nos tests sur différents modèles (Word2Vec, BERT...), nos comparatifs de performance et la justification de nos choix finaux.
*   **L'Architecture du Parser :** Comment nous transformons du code brut en données analysables (AST, Tokenization).
*   **Les Choix Techniques :** Front-end, Back-end, et intégration des composants.

---
*Projet réalisé dans le cadre de la SAE - IUT.*