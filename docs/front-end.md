# Langage et framework front‑end pour l’application FastAPI

Pour développer le front-end, c’est-à-dire l’aspect visuel de l’application, il est nécessaire de réfléchir aux langages, frameworks à utiliser. C’est pourquoi nous avons mené une réflexion approfondie sur le choix des technologies, afin de déterminer celles qui offrent les meilleures performances pour l’application tout en répondant aux besoins de l’utilisateur.


## Besoin du client

En ce qui concerne le front-end, le client souhaite une application fonctionnelle, mais également esthétique, agréable visuellement et moderne, tout en respectant la charte graphique de l’IUT.

## Présentation des frameworks front-end

Pour accompagner FastAPI et répondre aux besoins du client, plusieurs frameworks front-end modernes peuvent être envisagés.

- React est l’un des frameworks les plus populaires. Il repose sur JavaScript ou TypeScript et offre un écosystème très complet. Sa structure basée sur des composants réutilisables permet de concevoir des interfaces dynamiques et modulaires. Grâce à des bibliothèques comme Axios, React s’intègre parfaitement avec FastAPI pour des requêtes HTTP. Ce framework est idéal pour les applications modernes. Cependant, React est relativement lourd à mettre en place, surtout pour des petites applications, car il nécessite le chargement de nombreux fichiers JavaScript avant que l’application ne soit utilisable. Le navigateur doit télécharger, analyser et exécuter ce code, ce qui allonge le temps de chargement initial. De plus, l’utilisation de multiples bibliothèques et outils de configuration augmente la complexité technique du projet. Dans certains cas, des applications peuvent atteindre une taille de 2,3 Mo, ce qui témoigne d’une faible optimisation.


- Vue.js est un framework front-end basé sur JavaScript. Parmi ses principaux avantages, on trouve sa courbe d’apprentissage très accessible, sa documentation complète, et sa légèreté, qui le rendent idéal pour des projets de petite à moyenne envergure. Il offre également une bonne intégration avec des backends comme FastAPI avec sa gestion simple des appels API. Cependant, Vue présente aussi quelques inconvénients. En effet, son écosystème est plus restreint que celui de React et peut parfois limiter le choix de bibliothèques et d’outils.


- Preact est une version allégée de React, offrant la même syntaxe et les mêmes concepts mais avec un poids bien inférieur et des performances accrues. En effet, Preact est plus rapide parce qu’il utilise un Virtual DOM plus simple que React. Il fait moins de calculs et de vérifications avant de modifier le DOM réel, ce qui permet d’appliquer les changements plus rapidement et avec moins de code à exécuter. Il est compatible avec la plupart des bibliothèques React via preact/compat, il est idéal pour des applications légères et rapides. Une application avec `preact/compat` a une taille d'environ 9 ko. En résumé, Preact est l'équivalent de React sans ses défauts.

## Conclusion

Tous les frameworks front-end présentés utilisent le langage JavaScript. On peut donc en déduire que ce langage est adapté pour répondre aux besoins exprimés, notamment en matière d’interactivité, de dynamisme et d’intégration avec une API FastAPI.
Parmi ces frameworks, Preact apparaît comme le meilleur choix pour un projet de petite envergure, grâce à sa légèreté, ses excellentes performances et sa compatibilité avec l’écosystème React. Il offre ainsi la possibilité de bénéficier des avantages de React en réduisant les temps de chargement.
Son écosystème complet, sa facilité d’intégration et sa simplicité de mise en œuvre en font une solution particulièrement adaptée pour développer une interface moderne, fluide et performante en lien avec un backend FastAPI et qui répond parfaitement au besoin du client.

