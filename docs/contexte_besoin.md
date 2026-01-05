# Contexte et besoins du projet

## Utilisation des embeddings

L’intelligence artificielle, en particulier les LLM, est omniprésente parmi nous de nos jours. Cependant, pour que ceux-ci puissent répondre à nos demandes, ils doivent être capables de comprendre nos mots. Malheureusement, l’intelligence artificielle ne comprend que les nombres et les mathématiques. C’est pourquoi nos mots sont transformés en *tokens* — des mots ou des fractions de mots — qui sont ensuite convertis en vecteurs : ce sont les **embeddings**. Ces vecteurs sont très complexes et peuvent contenir des milliers de valeurs chacun.

En manipulant les embeddings, puis en les simplifiant en trois dimensions pour les observer dans l’espace, on peut constater de nombreuses choses intéressantes :

- **Contexte :** des mots utilisés dans le même contexte ou appartenant au même champ lexical se positionnent plutôt proches dans l’espace.  
- **Opérations :** on peut effectuer des opérations sur les vecteurs des mots et, en récupérant le vecteur du mot le plus proche du résultat, obtenir un mot cohérent.  
  Par exemple : `roi - homme + femme = reine`.  
  En détaillant, `roi - homme` fait ressortir le principe de la *royauté*, et si l’on ajoute `femme` à ce principe, on obtient naturellement `reine` :
  
  ![alt text](./img/contexte/roi-homme+femme.png){ width="400" .center }

Mais ces opérations ne se limitent pas à cela : on peut également appliquer des principes à des mots. Par exemple, si l’on ajoute le vecteur `synonyme` au vecteur `vite`, on obtiendra probablement un vecteur proche de celui de `rapide`.

## Application concrète

De ces constats est née l’idée d’appliquer ce principe à des cas plus concrets. C’est pourquoi nous avons travaillé sur la **suggestion intelligente de termes métier**, notamment pour le **nommage de variables** dans le cadre de la programmation, afin d’améliorer la lisibilité, la maintenabilité et l’auto-documentation du code.  
Dans un premier temps, il a donc été décidé de mieux comprendre la manipulation des embeddings, pour ensuite intégrer la suggestion intelligente dans différentes applications : un **glossaire métier** et une **extension d’environnement de développement**.

## Projet d’application « glossaire »

Le but du projet est de développer une **application de glossaire métier** qui permettra de saisir un mot et ses informations : définition, contexte, synonymes, antonymes, termes liés, etc.  
À cette application, il faudra ajouter des **suggestions intelligentes**, en utilisant l’intelligence artificielle et les embeddings, afin de compléter les informations d’un mot de manière cohérente et pertinente.

## Cibles et contraintes

Cette application est déstinée à différents types d'utilisateurs qui apportent leur lot de contraintes chacuns :

 - Les étudiants : Notre cliente étant enseignante à l'IUT, elle aimerait pouvoir utiliser l'application pour ces élèves. Pour les étudiants il y a deux cas : les ordinateurs de l'IUT ou le ordinateurs personnels. Pour les ordinateurs de l'IUT, l'application sera disponible depuis des machines virtuelles, il faut donc que l'application soit légère, et que le modèle d'IA soit suffisamment léger pour tourner en local sur ces petites machines virtuelles et ce sous Linux.
 Pour les étudiants qui utilisent une machine personnelle, il faut donc répondre à la même contrainte de puissance puisque certains ont de vieilles machines peu performantes. De plus il faut pouvoir faire tourner l'application sur tous les systèmes d'exploitation (Linux, Windows, MacOS)
 - Les entreprises : Notre cliente possède également un réseau avec des professionnels au sein d'entreprises qui sont intéressés par cette applications et qui aimeraient pouvoir l'utiliser pour leurs projets. Cela ne pose pas de contrainte de performance plus que cela, cependant les données qui sont insérées dans l'applications peuvent être sensibles (glossaire ou code), surtout puisqu'on utilise de l'IA. Cela impose de respecter la souveraineté des données et assurer qu'elles ne sont pas publiées partout dans des modèles d'IA ou autre.
 - Open-source : l'application est également déstinée à être open-source, pour permettre une évolution et des suggestions par la communauté et pour qu'elle puis être reprise et réutilisée par la suite pour d'autres projets de SAE ou projets de recherche. Cela impose de vérifier que notre utilisation d'outils externe comme les modèle d'IA ne rentre pas en conflit avec les certificats et les conditions d'utilisation de l'outils par exemple.