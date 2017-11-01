---
ID: 3786
post_title: Github en Bretagne, partie 1
author: Colin FAY
post_excerpt: ""
layout: post
permalink: >
  http://data-bzh.fr/github-bretagne-partie-1/
published: true
post_date: 2017-11-01 15:24:51
---
<h2>Première partie d'une exploration du réseau social de développeur, avec un focus sur la Bretagne (vous vous en doutiez).</h2>
<!--more-->

Réseau social fétiche des développeurs de tous poils, <strong>Github est une plateforme collaborative qui permet de partager d'abord du code</strong>, mais aussi des documents, ou encore des pages web. Vous pouvez retrouver le compte github de Data Bzh <a href="https://github.com/DataBzh">ici</a>, ainsi que celui de <a href="https://github.com/ColinFay">Colin</a> et celui de <a href="https://github.com/michelcaradec">Michel</a>.

Sur le Github de Data Bzh, vous trouverez notamment les codes qui ont été utilisés pour créer les articles du blog.
<h3>À propos des données</h3>
Nous avons collecté ces données en effectuant des requêtes sur l'API Github avec R. <strong>Au total, nous avons collecté 1838 profils différents sur 10 villes les plus peuplées de la région plus une requête sur la région</strong> — parmi ces résultats, 116 sont des organisations, et 1722 sont des utilisateurs.

[Tweet "#DataViz #Dev — #Github en #Bretagne, épisode 1"]
<h3>Les compagnies les plus représentées</h3>
Chaque profil peut indiquer appartenir à une société. Quelles sont les compagnies les plus représentées ?

<a href="http://data-bzh.fr/wp-content/uploads/2017/10/societe_github_bretagne.png"><img class="aligncenter size-full wp-image-3787" src="http://data-bzh.fr/wp-content/uploads/2017/10/societe_github_bretagne.png" alt="" width="1200" height="600" /></a>

En tête de gondole, Orange, avec plus de 20 utilisateurs enregistrés sur Github. Viennent ensuite EPAM Systems, une société de développement de logiciels (ce qui fait sens, donc), et Telecom Bretagne, une école d'ingénieurs.
<h3>Du monde à embaucher ?</h3>
Sur Github, il est possible d'afficher son "embauchabilité". <strong>Eh bien ce ne sont pas moins de 248 profils qui ont indiqués TRUE dans cet espace</strong>. Le reste ? Des données manquantes, ce qui reste indéterminé sur l'employabilité ou non des autres profils.
<h3>Qui sont les plus prolifiques ?</h3>
Sur la plateforme, les repositories (repo pour faire court) correspondent à des "sous dossier", que l'on peut envisager comme des projets à part entière, une unité de développement, une analyse, un module... Bref, un élément autonome de code.

Quelle répartition du nombre de repos par utilisateur ?

<a href="http://data-bzh.fr/wp-content/uploads/2017/11/repos_users_github_bzh.png"><img class="aligncenter size-full wp-image-3795" src="http://data-bzh.fr/wp-content/uploads/2017/11/repos_users_github_bzh.png" alt="" width="1200" height="600" /></a>

Globalement, les utilisateurs ne s'envolent que très rarement au delà de 10 repos... Avec un pic à 300 repos. Alors, qui sont ceux qui publient le plus ?

|login | public_repos|
|:--------------|:------------|
|ndeloof | 300|
|FGRibreau | 203|
|Natim | 183|
|thomasleveil | 163|
|almet | 157|
|ybonnel | 121|
|LostInBrittany | 121|
|pierrecarre | 119|
|barais | 116|
|nledez | 115|
<h3>Utilisateurs les plus suivis ?</h3>
En moyenne, les utilisateurs affichent 5,3 followers, avec un écart-type de 31,8... Un écart-type important qui reflète une large inégalité de la répartition de la popularité : en effet, l'utilisateur le plus suivi est AliSoftware, avec pas moins de 950 followers.

Voici les développeurs les plus suivis :

<a href="http://data-bzh.fr/wp-content/uploads/2017/11/user_suivis_github_bzh.png"><img class="aligncenter size-full wp-image-3796" src="http://data-bzh.fr/wp-content/uploads/2017/11/user_suivis_github_bzh.png" alt="" width="1200" height="600" /></a>
<h3>Et côté bio ?</h3>
Non, rien à voir avec l'appellation agricole, nous faisons ici référence aux biographies des utilisateurs, qui sont fournis par 434 profils.

Quels sont les termes les plus fréquents ?

|word | n|
|:-----------|:----|
|developer | 77|
|student | 73|
|web | 48|
|rennes | 37|
|engineer | 36|
|software | 35|
|computer | 26|
|france | 24|
|engineering | 21|
|front | 21|

Sans surprise, une forte présence des termes clés du développement, en particulier web, et spécifiquement le front (en référence au développement front-end) et le software.
<h3>Un tour du côté des repos</h3>
Comme nous le disions plus haut, un repos est un dossier spécifique créé sur GitHub. Dans notre échantillons, 318 inscrits n'ont ouvert aucun repo sur le réseau social. Nous nous intéresserons donc aux 1520 autres.
<h4>Combien de repos ?</h4>
Au total, notre recherche sur l'API a permis de recueillir<strong> 13154 repositories pour Github en Bretagne.</strong> Sur cette base, 5300 sont des forks — les forks sont des copies sur son compte de repositories créés par d'autres, afin d'utiliser, d'améliorer ou de modifier un code écrit par un autre développeur.
<h4>Les langages les plus utilisés</h4>
Chaque repos est étiqueté d'un langage, c'est-à-dire du langage de programmation du code contenu dans ce repos. Quels sont ceux que le retrouve le plus en Bretagne ?

<a href="http://data-bzh.fr/wp-content/uploads/2017/11/langage-repos.png"><img class="aligncenter size-full wp-image-3798" src="http://data-bzh.fr/wp-content/uploads/2017/11/langage-repos.png" alt="" width="1200" height="600" /></a>

Langage ultra populaire, JavaScript se trouve en tête de gondole avec pas moins de 2500 repos. On retrouve ensuite Java, Python, PHP, HTML et CSS, cinq langages eux aussi très populaires.
<h4>Les repos les plus populaires</h4>
<strong>Deux indicateurs permettent de mesurer la popularité d'un repo : les stars, qui sont l'équivalent de mise en favoris, et le watch, qui est un bouton permettant de surveiller l'activité sur un repo</strong>. L'API Github ne nous a pas retourné les volumes de stars, nous avons cependant le nombre de "watchers" de chaque repos.

Voici donc les plus surveillés :
|full_name |language | watchers_count|
|:------------------------------|:----------|--------------:|
|aterrien/jQuery-Knob |JavaScript | 5071|
|Okazari/Rythm.js |JavaScript | 2815|
|aurelhubert/ahbottomnavigation |Java | 2464|
|gildas-lormeau/zip.js |JavaScript | 1742|
|matcornic/hermes |Go | 1024|
|Lawouach/WebSocket-for-Python |Python | 860|
|neveldo/jQuery-Mapael |JavaScript | 827|
|ganfra/MaterialSpinner |Java | 746|
|FGRibreau/check-build |JavaScript | 700|
|citronneur/rdpy |Python | 614|
<h4>Date de création des repos</h4>
Et dans l'ensemble, sont-ce des repos récents ou plutôt datant ?

Les plus vieux repos étant :

|full_name |language |created_at |
|:----------------------------------|:----------|:-------------------|
|iMax-pp/pintme |Python |2009-01-31 08:23:54 |
|deruelle/mobicents |Java |2009-02-13 16:59:02 |
|rayene/littlepiggies |Python |2009-02-25 10:39:43 |
|Indiana-/upload_progress |Ruby |2009-05-13 09:09:32 |
|iMax-pp/Haiku-Browser |C++ |2009-05-19 09:18:33 |
|stanguy/scripts |Python |2009-05-23 12:43:57 |
|organicweb/limonade-wiki-example |PHP |2009-06-03 10:14:18 |
|iMax-pp/Reactive-Systems-Simulator |C++ |2009-07-14 16:04:15 |
|stanguy/emacs.d |Emacs Lisp |2009-08-03 19:37:18 |
|dchapillon/rennes-on-rails |Ruby |2009-08-04 09:08:21

Et quand on compare update et date de création ?

<a href="http://data-bzh.fr/wp-content/uploads/2017/11/crea_update_repos_github_bzh.png"><img class="aligncenter size-full wp-image-3802" src="http://data-bzh.fr/wp-content/uploads/2017/11/crea_update_repos_github_bzh.png" alt="" width="1200" height="1200" /></a>

On remarque que dans l'ensemble, les repos sont relativement mis à jour. Alors que certains ont été créés avant 2013, aucun n'affiche une date de mise à jour antérieur à cette date. Cependant, au vu du pic le premier mois de janvier, on peut s'interroger sur la justesse des résultats de l'API — ce fameux pic pourrait signifier un bug affectant toutes les mises à jour antérieures à cette date.
<h4>Les descriptions</h4>
Alors, de quoi est-il question dans ces repos ? Rapide text-mining des descriptions :

|word | n|
|:-----------|:---|
|project | 447|
|web | 440|
|simple | 403|
|library | 390|
|application | 351|
|plugin | 345|
|based | 314|
|javascript | 313|
|api | 288|
|python | 276|
<h4>Et enfin : petit ou gros projet ?</h4>
L'API de Github renvoie la taille de chaque projet.

<strong>Alors, quels sont les plus gros projets sur Github Bretagne ?</strong>

|full_name |language | size|
|:----------------------------|:-----------------------|:-------|
|needpower/0ad |C++ | 3118158|
|saoudimassi/Arduino-1 |HTML | 2855094|
|mboussaa/HXvariability |NA | 2816538|
|YoannGUILLO/azure-docs |GCC Machine Description | 2458877|
|eldruz/wesnoth |C++ | 1974034|
|Yannleonard/azure-docs.fr-fr |HTML | 1503584|
|jjehannet/xbmc |C++ | 1432943|
|BrittiaGuiriec/linux |C | 1361168|
|Watilin/YouTubeCenter |HTML | 1352637|
|strnk/linux-xlnx |C | 1352385|
<h3>Retrouvez nous sur Github</h3>
Et comme d'habitude, retrouvez le code R qui a servi à réaliser ce post sur <a href="https://github.com/DataBzh/social-media">notre Github</a> !