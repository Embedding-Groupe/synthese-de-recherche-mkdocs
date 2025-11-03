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