---
ID: 3417
post_title: >
  Bretagne — Votes blancs et nuls aux
  Présidentielles de 1965/2017
author: Colin FAY
post_excerpt: ""
layout: post
permalink: >
  http://data-bzh.fr/vote-blanc-aux-presidentielles-en-bretagne-19652017/
published: true
post_date: 2017-05-02 14:00:21
---
<h2>Aperçu du vote blanc et nul en Bretagne administrative, des présidentielles 1965 à celles de 2017.<!--more--></h2>
<h3>À propos du jeu de données</h3>
Dans ce billet, nous avons couplé deux jeux de données : <a href="https://www.data.gouv.fr/fr/datasets/elections-presidentielles-1965-2012-1/" target="_blank" rel="noopener noreferrer">Elections présidentielles 1965-2012</a>, fourni par SciencesPo, et <a href="https://github.com/datactivist/presidentielle2017/raw/master/Presidentielle_2017_Resultats_BV_T1_clean_def.csv" target="_blank" rel="noopener noreferrer">Election présidentielle des 23 avril et 7 mai 2017 - Résultats définitifs du 1er tour par bureaux de vote</a>, d'abord mis en ligne sur data.gouv au format txt, avant d'être rendu disponible en csv sur le GitHub de Datactivist.

Note : le jeu de données libéré par SciencesPo ne comporte pas une colonne avec les votes blancs, mais <strong>combine blancs et nuls</strong>. Nous avons donc reproduit ce schéma sur le jeu de données de 2017.

Quelle différence entre ces deux types de votes ? Le <strong>vote blanc consiste au dépôt d'une enveloppe vide ou avec un bulletin blanc</strong>, là où le <strong>vote nul regroupe l'ensemble des bulletins "non recevables"</strong> : annotations, non-conformité, déchirures... (<a href="http://www.vie-publique.fr/decouverte-institutions/citoyen/participation/voter/droit-vote/abstention-vote-blanc-vote-nul-quelles-differences.html">plus d'infos</a>) On peut cependant considérer l'intention semblable, du moins sur le plan statistique : un votant déposant une enveloppe vide sait que son bulletin aura le même impact qu'un bulletin raturé.
<h3>Le vote blanc et nul en Bretagne Administrative</h3>
En Bretagne, il y a en moyenne <strong>2,53% d'abstention à chaque suffrage</strong>, avec un plus fort taux d'abstention au second tour (1,61 en moyenne pour le premier vote, contre 3,5 au second).

<a href="http://data-bzh.fr/wp-content/uploads/2017/05/votes-blancs-bretagne.png"><img class="aligncenter size-full wp-image-3420" src="http://data-bzh.fr/wp-content/uploads/2017/05/votes-blancs-bretagne.png" alt="Vote blanc en Bretagne" width="1200" height="600" /></a>

Le <strong>plus haut taux d'abstention a été atteint en 2012</strong>, au second tour, avec 5,3 % de votes blancs et nuls — pour rappel, il s'agit de l'élection qui a opposé François Hollande à Nicolas Sarkozy. Une année suivie de près par 2002 et 1969, qui affichent respectivement des taux de votes blancs ou nuls de 5,09 et 5,08 %.

Sur ce graphique, nous constatons également que <strong>le second tour (en vert) compte systématiquement plus de votes blancs et nuls que le premier tour (en bordeaux)</strong>. Est-ce lié à une différence de nombre de votants ?

<a href="http://data-bzh.fr/wp-content/uploads/2017/05/nombre-votants-bretagne.png"><img class="aligncenter size-full wp-image-3421" src="http://data-bzh.fr/wp-content/uploads/2017/05/nombre-votants-bretagne.png" alt="nombre votant aux presidentielles" width="1200" height="600" /></a>

Ici, pas de tendance notable : le nombre de votants est sensiblement le même d'un tour à l'autre, et la progression à travers les années est une augmentation structurelle — le nombre d'habitants en France, et donc par extension le nombre de votants potentiels, étant en constante augmentation.
<h3>La Bretagne et la France</h3>
La tendance aux votes blancs et nuls de Bretagne est-elle représentative du vote français ? Comparons ces deux périmètres.

<a href="http://data-bzh.fr/wp-content/uploads/2017/05/vote-blanc-bretagne-comparé-france.png"><img class="aligncenter size-full wp-image-3422" src="http://data-bzh.fr/wp-content/uploads/2017/05/vote-blanc-bretagne-comparé-france.png" alt="" width="1200" height="600" /></a>

Note : pour vraiment dégager deux tendances exclusives, nous avons choisi de représenter en vert la tendance de tous les départements sauf la Bretagne administrative.

Nous pouvons constater que <strong>l'évolution dans ces deux périmètres est quasi semblable</strong>. L'autre tendance ? Systématiquement,  le pourcentage de votes blancs et nuls en Bretagne est inférieur à celui du reste du pays. Vérifions en projetant les pourcentages pour tous les départements de France.

<a href="http://data-bzh.fr/wp-content/uploads/2017/05/vote-blanc-nuls.png"><img class="aligncenter size-full wp-image-3426" src="http://data-bzh.fr/wp-content/uploads/2017/05/vote-blanc-nuls.png" alt="" width="1200" height="600" /></a>

La Bretagne reste ainsi un département à faible taux de votes blancs ou nuls, en comparaison aux autres département de France.
<h3>Par département</h3>
Qu'en est-il si nous regardons du côté des départements ?

<a href="http://data-bzh.fr/wp-content/uploads/2017/05/blancs-nuls-departement.png"><img class="aligncenter size-full wp-image-3425" src="http://data-bzh.fr/wp-content/uploads/2017/05/blancs-nuls-departement.png" alt="vote blancs nuls par département" width="1200" height="600" /></a>

Pas de tendance remarquable du côté des départements — même si l'Ille-et-Vilaine semble en tête de l'abstention (mais de peu) au premier tour, aucun motif ne se dessine au second tour.

Et maintenant ? Attendre le résultat du second tour pour mettre à jour cet article !

Retrouvez le code utilisé dans ce billet sur notre <a href="https://github.com/DataBzh/territoire" target="_blank" rel="noopener noreferrer">GitHub</a>.