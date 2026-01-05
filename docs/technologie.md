# Choix des technologies pour l'application

## FastAPI

FastAPI est un framework web moderne pour Python, conçu pour créer des API. Il est particulièrement apprécié pour sa rapidité d’exécution, proche de celle de Node.js ou Go, et sa facilité d’utilisation qui permet d’écrire du code clair. Grâce à la déclaration de types Python, FastAPI génère automatiquement une documentation interactive.


Initialement, nous avions envisagé de développer notre application sous forme de site web. Cette approche semblait pratique pour un accès rapide depuis n’importe quel appareil. Cependant, après réflexion, elle présentait un inconvénient majeur : la souveraineté des données.

La souveraineté des données c'est le fait pouvoir garder le contrôle sur ses informations, savoir où elles sont stockées et qui peut y accéder, afin de protéger leur confidentialité et leur sécurité.

En effet, notre application devait être utilisée à la fois par des étudiants de l’IUT et par des utilisateurs externes. Un site web impliquait de stocker les données sur des serveurs distants, ce qui pouvait poser des problèmes de sécurité et de confidentialité.

Nous avons donc étudié plusieurs alternatives, et finalement, nous avons opté pour une application de bureau. Cette solution présente plusieurs avantages.Tout d'abord les données peuvent être stockées localement, garantissant un meilleur contrôle et une meilleure confidentialité. De plus l’application reste accessible aux étudiants de l’IUT comme aux utilisateurs externes, sans dépendre d’un hébergement web.

Ainsi, le choix de l’application de bureau répond à nos exigences en termes de sécurité, de souveraineté des données et d’accessibilité.

## Choix de la technologie pour l’application de bureau

Pour développer notre application de bureau, nous avons comparé plusieurs solutions : Flet, Electron et Tauri. Premièrement, Flet est très récent et présente donc une documentation limitée, ce qui rend son utilisation risquée pour le projet. Ensuite, Electron, très populaire, est facile à utiliser mais consomme en moyenne 200 à 300 Mo de RAM au démarrage, contre seulement 30 à 50 Mo pour Tauri, ce qui impacte les performances. À l’inverse, Tauri combine légèreté, performance et documentation suffisamment complète, ce qui nous garantis une bonne expérience utilisateur. De plus, au lancement de l'application, Tauri s’est avéré 3 à 4 fois plus rapide au démarrage que Flet et Electron sur des machines standards. C’est donc ce choix que nous avons retenue pour notre projet.