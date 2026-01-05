# Choix des technologies pour l'application

## FastAPI

FastAPI est un framework web moderne pour Python, conçu pour créer des API. Il est particulièrement utilisé pour sa rapidité d’exécution, proche de celle de Node.js ou Go, et sa facilité d’utilisation qui permet d’écrire du code clair. Grâce à la déclaration de types Python, FastAPI génère automatiquement une documentation interactive.


## Le type d'application

Initialement, nous avions envisagé de développer notre application sous forme de site web. Cette approche semblait idéale, car le client souhaitait une application accessible rapidement par tous, depuis n’importe quel appareil. Cependant, après réflexion, elle présentait un inconvénient majeur : la souveraineté des données.

La souveraineté des données c'est le fait pouvoir garder le contrôle sur ses informations, savoir où elles sont stockées et qui peut y accéder, afin de protéger leur confidentialité et leur sécurité.

En effet, notre application devait être utilisée à la fois par des étudiants de l’IUT et par des utilisateurs externes. Un site web impliquait de stocker les données sur des serveurs distants, ce qui pouvait poser des problèmes de sécurité et de confidentialité.

Nous avons donc étudié plusieurs alternatives, et finalement, nous avons opté pour une application de bureau. Cette solution présente plusieurs avantages.Tout d'abord les données peuvent être stockées localement, garantissant un meilleur contrôle et une meilleure confidentialité. De plus l’application reste accessible aux étudiants de l’IUT comme aux utilisateurs externes, sans dépendre d’un hébergement web.

Ainsi, le choix de l’application de bureau répond à nos exigences en termes de sécurité, de souveraineté des données et d’accessibilité.

## Choix de la technologie pour l’application de bureau

Après le choix d'opter pour une application de bureau nous avons réfléchis à quel technologie nous allons utilisé pour la développer.

C'est pourquoi nous avons comparé plusieurs solutions : Flet, Electron et Tauri. Premièrement, Flet est très récent et présente donc une documentation limitée, ce qui rend son utilisation risquée pour le projet. En effet, la première version de Flet considérée comme stable est sortie en 2025. Ensuite, Electron est très populaire car il est utilisé par des applications réputées comme Discord, ce qui témoigne de sa fiabilité. De plus, il est facile à prendre en main. Cependant, il consomme en moyenne 200 à 300 Mo de RAM au démarrage, contre seulement 30 à 50 Mo pour Tauri, ce qui peut impacter les performances. À l’inverse, Tauri combine légèreté, performance et documentation suffisamment complète, ce qui nous garantis une bonne expérience utilisateur. De plus, au lancement de l'application, Tauri s’est avéré 3 à 4 fois plus rapide au démarrage que Flet et Electron sur des machines standards. Tauri n’est pas encore aussi largement adopté que Electron mais il existe des applications connus qui ont été développées avec Tauri.Par exemple Zed, un éditeur de code, et Nota, une application de prise de notes basée sur Markdown.

## Embarquement de l'intelligence artificielle locale

Puisqu'on utilise une IA qui tourne en local pour l'application il faut embarquer l'IA dans celle-ci. On a vu deux options pour cela, soit embarquer directement le modèle via un fichier .gguf qui permet de contenir un modèle directement. Mais cette approche réduit largement les performances du modèle. Donc on est passé par une autre approche : Ollama, qui permet de télécharger un grand nombre de modèles et de les faire tourner en local très facilement. Le seul inconvénient est d'installer l'application Ollama, c'est pourquoi on détecte la présence d'Ollama et on propose de l'installer s'il n'est pas présent sur l'ordinateur. Cela présente également un autre avantage, on peut changer de modèle très facilement et proposer cette option à l'avenir pour permettre d'utiliser un plus gros modèle pour de meilleurs performance si l'utilisateur à un ordinateur plus puissant.


## Conclusion

Au terme de notre analyse, Tauri s’est imposé comme la solution la plus adaptée pour notre application de bureau. Son équilibre entre performance, légèreté et fiabilité en fait un choix pertinent pour offrir une expérience utilisateur optimale tout en garantissant la sécurité et la gestion des données.
Parallèlement, FastAPI nous permet de gérer efficacement le back-end de l’application, grâce à sa rapidité, sa clarté et la génération automatique de documentation, assurant ainsi une communication fluide entre l’interface et les données.

