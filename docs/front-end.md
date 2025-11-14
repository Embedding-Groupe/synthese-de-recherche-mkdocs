# Framework front-end pour l'application FastAPI

## FastAPI

FastAPI est un framework web moderne pour Python, conçu pour créer des API. Il est particulièrement apprécié pour sa rapidité d’exécution, proche de celle de Node.js ou Go, et sa facilité d’utilisation qui permet d’écrire du code clair. Grâce à la déclaration de types Python, FastAPI génère automatiquement une documentation interactive.

## Besoin du client

Le client souhaite une application fonctionnelle, mais également esthétique, agréable visuellement et moderne.

## Présentation de Framework front-end

Pour accompagner FastAPI et répondre aux besoins du client, plusieurs frameworks front-end modernes peuvent être envisagés.

- React est l’un des frameworks les plus populaires. Il repose sur JavaScript ou TypeScript et offre un écosystème très complet. Sa structure basée sur des composants réutilisables permet de concevoir des interfaces dynamiques et modulaires. Grâce à des bibliothèques comme Axios, React s’intègre parfaitement avec FastAPI pour des requêtes HTTP. Ce framework est idéal pour les applications modernes. Cependant React est lourd à mettre en place cela entraîne des temps de chargement plus longs et une complexité technique accrue.

- Vue.js est un framework front-end basé sur JavaScript. Parmi ses principaux avantages, on trouve sa courbe d’apprentissage très accecible, sa documentation  complète, et sa légèreté, qui le rendent idéal pour des projets de petite à moyenne envergure. Il offre également une bonne intégration avec des backends comme FastAPI avec à sa gestion simple des appels API. Cependant, Vue présente aussi quelques inconvénients. En effet, son écosystème est plus restreint que celui de React et peut parfois limiter le choix de bibliothèques et d’outils.

- Preact est une version allégée de React, offrant la même syntaxe et les mêmes concepts mais avec un poids bien inférieur et des performances accrues. Il est Compatible avec la plupart des bibliothèques React via preact/compat, il est idéal pour des applications légères et rapides. En resumé, Preéact est l'équivalent de React sans ses defaults.

## Conclusion

Tous les frameworks front-end présenté utilisent le langage JavaScript. On peut donc en déduire que ce langage est idéal pour répondre aux besoins exprimés, notamment en matière d’interactivité, de dynamisme et d’intégration avec une API FastAPI.
Parmi ces frameworks, Preact apparaît comme le meilleur choix pour un projet de petite envergure, grâce à sa légèreté, ses excellentes performances et sa compatibilité avec l’écosystème React. Il offre ainsi la possibilité de bénéficier des avantages de React en réduisant les temps de chargement.
Son écosystème complet, sa facilité d’intégration et sa simplicité de mise en œuvre en font une solution particulièrement adaptée pour développer une interface moderne, fluide et performante en lien avec un backend FastAPI.


# Choix de la technologie

Initialement, nous avions envisagé de développer notre application sous forme de site web. Cette approche semblait pratique pour un accès rapide depuis n’importe quel appareil. Cependant, après réflexion, elle présentait un inconvénient majeur : la souveraineté des données.

La souveraineté des données c'est le fait pouvoir garder le contrôle sur ses informations, savoir où elles sont stockées et qui peut y accéder, afin de protéger leur confidentialité et leur sécurité.

En effet, notre application devait être utilisée à la fois par des étudiants de l’IUT et par des utilisateurs externes. Un site web impliquait de stocker les données sur des serveurs distants, ce qui pouvait poser des problèmes de sécurité et de confidentialité.

Nous avons donc étudié plusieurs alternatives, et finalement, nous avons opté pour une application de bureau. Cette solution présente plusieurs avantages.Tout d'abord les données peuvent être stockées localement, garantissant un meilleur contrôle et une meilleure confidentialité. De plus l’application reste accessible aux étudiants de l’IUT comme aux utilisateurs externes, sans dépendre d’un hébergement web.

Ainsi, le choix de l’application de bureau répond à nos exigences en termes de sécurité, de souveraineté des données et d’accessibilité.

## Choix de la technologie pour l’application de bureau

Pour développer notre application de bureau, nous avons comparé plusieurs solutions : Flet, Electron et Tauri. Premièrement, Flet est très récent et présente donc une documentation limitée, ce qui rend son utilisation risquée pour le projet. Ensuite, Electron, très populaire, est facile à utiliser mais consomme en moyenne 200 à 300 Mo de RAM au démarrage, contre seulement 30 à 50 Mo pour Tauri, ce qui impacte les performances. À l’inverse, Tauri combine légèreté, performance et documentation suffisamment complète, ce qui nous garantis une bonne expérience utilisateur. De plus, au lancement de l'application, Tauri s’est avéré 3 à 4 fois plus rapide au démarrage que Flet et Electron sur des machines standards. C’est donc ce choix que nous avons retenue pour notre projet.