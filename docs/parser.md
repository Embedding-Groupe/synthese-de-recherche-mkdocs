# **Récupération des mots‑clés (Parser)**

## Contexte d'utilisation
Dans le cadre de notre application, nous souhaitons analyser des fichiers de code source afin d'en extraire les concepts clés (les noms de variables, fonctions, classes, etc.). L'objectif est de transformer un code brut en une liste structurée de mots significatifs pondérés par leur fréquence. Ces données sont destinées à alimenter une intelligence artificielle ou un moteur de recherche interne, permettant de classifier ou de résumer le contenu technique d'un projet. De plus, elles nous serviront plus tard pour pouvoir vérifier si tous les mots d'un glossaire sont présents dans le code, à la manière d'un linter.

## Solutions envisagées
Pour parvenir à extraire ces informations, plusieurs approches ont été considérées :

1.  **Utilisation d'Expressions Régulières (Regex) :**
    *   *Principe :* Rechercher des motifs textuels correspondant à des variables ou des fonctions.
    *   *Problème :* Très complexe à maintenir, difficulté à distinguer le code des commentaires ou des chaînes de caractères, et manque de fiabilité sur des structures complexes.

2.  **Traitement de chaînes simples (String Manipulation) :**
    *   *Principe :* Découper le fichier par espaces ou retours à la ligne.
    *   *Problème :* Ne comprend pas la syntaxe du langage (mélange mots-clés du langage et noms de variables), très bruité.

3.  **Analyse Syntaxique (Parsing AST) :**
    *   *Principe :* Utiliser les outils natifs du langage pour transformer le code en un Arbre Syntaxique Abstrait (Abstract Syntax Tree).
    *   *Avantage :* Permet de comprendre structurellement le code (savoir ce qui est une fonction, une classe, une variable) et d'ignorer proprement la syntaxe pure (parenthèses, mots-clés comme `def`, `class`).

## Solution retenue
Nous avons opté pour la **solution basée sur l'AST (Abstract Syntax Tree)**. 

*   **Fiabilité :** C'est la méthode la plus robuste car elle utilise le même mécanisme que l'interpréteur Python lui-même. Elle garantit que nous n'extrayons que des identifiants valides.
*   **Exemples connus :** Cette technique est utilisée par la majorité des outils d'analyse statique de code comme *Pylint*, *Black* ou les IDE pour l'autocomplétion.
*   **Bonus :** Cette technique est compatible avec plusieurs langages, dont certains sont vérifiés (C#, Go, Java, JavaScript, Python, etc.) et d'autres sont maintenus par des utilisateurs (Delphi, Ruby, PHP, etc.).

## Difficultés rencontrées
La mise en œuvre a présenté quelques défis :

*   **Distinction Identifiants vs Mots-clé :** Il fallait s'assurer de ne récupérer que les noms choisis par le développeur (noms de variables, fonctions) et non les mots réservés du langage (`while`, `import`, etc.).

*   **Conventions de nommage hétérogènes :** Le code peut utiliser différentes conventions (snake_case, camelCase). Un identifiant comme `calcul_moyenne` doit être compris comme deux mots : "calcul" et "moyenne".

*   **Chaînes ou commentaires :** En effet, les chaînes de caractères et les commentaires peuvent contenir des mots, mais nous ne souhaitons pas systématiquement les récupérer, car ils sont souvent utilisés dans un contexte différent du code et peuvent devenir des faux positifs. Si l'on souhaite les garder, on pourrait envisager d'appliquer un coefficient de priorité en fonction de la source du mot (important si c'est une variable, faible si c'est un commentaire ou une chaîne de caractères).

*   **Gestion des fichiers :** Orchestrer la lecture du fichier source, le passage des données entre les différentes étapes, et l'écriture du résultat final.

## Implémentation technique
La solution a été implémentée sous la forme d'un pipeline composé de 4 scripts Python distincts, exécutés séquentiellement.

### 1. Orchestrator (`orchestrator.py`)
C'est le chef d'orchestre. Il ne réalise pas de traitement mais coordonne l'appel des autres scripts.
*   *Fonctionnement :* Il prend en entrée le fichier source, appelle séquentiellement l'extracteur, le découpeur, et l'analyseur de fréquence. Il gère le flux de données entre chaque étape pour s'assurer que la sortie de l'un devient l'entrée du suivant.

### 2. Extractor (`extraction.py`)
Ce script est responsable de l'analyse syntaxique pure.
*   *Fonctionnement :* Il lit le fichier source Python et utilise le module `ast` pour parcourir l'arbre syntaxique. Il visite les nœuds du code (fonctions, classes, assignations) pour extraire tous les noms d'identifiants, en filtrant automatiquement les mots-clés du langage.

### 3. Splitter (`splitter.py`)
Ce script traite les chaînes de caractères brutes extraites.
*   *Fonctionnement :* Il prend une liste d'identifiants (ex: `userController`, `get_user_id`) et les décompose en mots unitaires (`user`, `Controller`, `get`, `id`). Il gère les différentes casses :
    *   **snake_case** (séparation par underscores)
    *   **camelCase** / **PascalCase** (séparation par majuscules)
    *   **kebab-case** (si présent)

### 4. Frequency Analyzer (`frequency.py`)
Ce dernier script compile les résultats.
*   *Fonctionnement :* Il compte les occurrences de chaque mot normalisé.
*   *Sortie :* Il génère un fichier JSON final (nommé d'après le fichier source) contenant les statistiques, par exemple : `{"user": 5, "controller": 2, "id": 8}`.

## Suite et Perspectives
Actuellement, le système est fonctionnel mais présente certaines limitations qui vont devoir être corrigées et améliorées pour la suite du projet :

*   **Support multi-langages :** Pour l'instant, seul le langage **Python** est pris en charge (car nous utilisons le module `ast` spécifique à Python). Pour supporter **PHP, Java, C++, ou C#**, nous devrons implémenter des extracteurs spécifiques à chaque langage ou utiliser une librairie de parsing polyglotte (comme *Tree-sitter*).
*   **Intégration Front-end :** Ces scripts fonctionnent actuellement en ligne de commande (CLI) ou via l'orchestrateur en backend. Ils ne sont pas encore connectés à l'interface utilisateur. Une API devra être créée pour permettre au front-end d'envoyer un fichier et de recevoir l'analyse JSON en retour.
*   **Lecture d'un programme entier :** Actuellement, le programme n'analyse qu'un fichier donné à la fois ; l'objectif est qu'il puisse recevoir un chemin ou un dossier source et parcourir l'entièreté du dossier pour analyser tous les fichiers du langage concerné.