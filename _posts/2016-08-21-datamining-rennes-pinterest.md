---
ID: 1361
post_title: '#DataMining — Rennes sur Pinterest'
author: Colin FAY
post_excerpt: ""
layout: post
permalink: >
  http://data-bzh.fr/datamining-rennes-pinterest/
published: true
post_date: 2016-08-21 18:00:49
---
<h2>Comment la ville de Rennes est-elle vue sur Pinterest ? Exploration avec R d'une sélection de dix comptes rennais présents sur le réseau social.</h2>
<!--more-->
<p style="text-align: right;"><em>Note : vous pouvez cliquer sur les images pour les agrandir.</em></p>

<h3>Rennes par Pinterest — Comptes et outils</h3>
Pour ce billet, nous nous intéressons à une sélection de 10 comptes Pinterest touchant à la ville de Rennes :
- <a href="https://www.pinterest.com/bibliothequeUR2/" target="_blank">Bibliothèques Université Rennes 2</a>
- <a href="https://www.pinterest.com/lairedu/" target="_blank">L'aire d'u - Université Rennes 2</a>
- <a href="https://www.pinterest.com/operaderennes/" target="_blank">Opéra de Rennes</a>
- <a href="https://www.pinterest.com/rennesmetropole/" target="_blank">Rennes Métropole</a>
- <a href="https://www.pinterest.com/renneswebtv/" target="_blank">Rennes Bretagne-Télé</a>
- <a href="https://www.pinterest.com/veilledoc_r2/" target="_blank">VeilleDoc_Rennes 2</a>
- <a href="https://www.pinterest.com/rennescoeur/" target="_blank">Rennes à coup de coeur</a>
- <a href="https://www.pinterest.com/tourismerennes/" target="_blank">Tourisme Rennes</a>
- <a href="https://www.pinterest.com/rennestv/" target="_blank">Rennes TV</a>
- <a href="https://www.pinterest.com/busanterennes/" target="_blank">bu santé Rennes1</a>

Les analyses qui suivent ont été réalisées avec R. La collecte a été faite le 15 aout 2016 à 21.00 grâce à <a href="https://cran.r-project.org/web/packages/rpinterest/index.html" target="_blank">rpinterest</a>, un package de data-mining qui permet d'accéder à l'API du réseau social.
<h3>Aperçu des dix comptes</h3>
<h4>Épingles, tableaux et abonnés</h4>
<a href="http://dev.data-bzh.fr/wp-content/uploads/2016/08/pins-boards-followers-2.jpeg"><img class="aligncenter wp-image-1362 size-full" src="http://dev.data-bzh.fr/wp-content/uploads/2016/08/pins-boards-followers-2.jpeg" alt="Rennes Pinterest : pins boards et followers" width="1200" height="600" /></a>

En moyenne, ces <strong>dix comptes ont épinglé 102 contenus</strong>, avec un maximum de 219 pour veilledoc_r2, et un minimum de 16 pour renneswebtv. Le compte le plus suivi, avec 272 followers, est rennescoeur, le moins suivi est bibliothequeUR2 (11 followers) — pour une<strong> moyenne globale de 114 followers</strong>. busanterennes a créé 34 boards, et rennesmetropole un seul, la moyenne étant de <strong>8 boards par compte</strong>.

Parmi les dix comptes étudiés ici, 2 sont classés en "business" (tourismerennes et busanterennes), les autres en "individual".
<h4>Abonnés et abonnements</h4>
<h4><a href="http://dev.data-bzh.fr/wp-content/uploads/2016/08/followers-following-2.jpeg"><img class="aligncenter wp-image-1381 size-full" src="http://dev.data-bzh.fr/wp-content/uploads/2016/08/followers-following-2.jpeg" alt="Abonnés et abonnements" width="1200" height="600" /></a></h4>
Au sein de notre population, et mis à part le compte rennescoeur, <strong>la variable followers (abonnés) apparait comme impactée par la variable following (abonnements)</strong> — en d'autres termes, plus le compte s'abonne à d'autres utilisateurs Pinterest, plus il est suivi.
<h4>Date de création des comptes</h4>
<img class="aligncenter size-full wp-image-1363" src="http://dev.data-bzh.fr/wp-content/uploads/2016/08/age-jour-comptes-pinterest-2.jpeg" alt="Date de création des comptes Pinterest" width="1200" height="600" />

En moyenne, la différence entre le jour de collecte des données (15 aout 2016) et la date de création des comptes est de 1085 jours — soit <strong>un peu moins de trois ans</strong>. Le compte le plus ancien est veilledoc_r2, créé le 15 janvier 2012 (c'est aussi celui qui compte le plus d'épingles), le plus récent est rennesmetropole, créé le 09 mai 2016.
<h3>Les boards</h3>
Au total, les tableaux créés par les comptes combinent 1018 épingles — 1009 images et 9 vidéos, avec une moyenne de 14 épingles par tableaux. En moyenne, <strong>les épingles sont likées 0,15 fois</strong>.
<h4><a href="http://dev.data-bzh.fr/wp-content/uploads/2016/08/tableaux-plus-epingles-2.jpeg"><img class="aligncenter size-full wp-image-1371" src="http://dev.data-bzh.fr/wp-content/uploads/2016/08/tableaux-plus-epingles-2.jpeg" alt="Les tableaux avec le plus d'épingles" width="1200" height="600" /></a>Les mots les plus utilisés dans les descriptions des boards sont :</h4>
<a href="http://dev.data-bzh.fr/wp-content/uploads/2016/08/mots-frequents-boards-2.jpeg"><img class="aligncenter size-full wp-image-1380" src="http://dev.data-bzh.fr/wp-content/uploads/2016/08/mots-frequents-boards-2.jpeg" alt="Mots les plus fréquents dans les description des boards" width="1200" height="600" /></a>La forte présence du terme "ouvrage" s'explique par deux facteurs :
- une forte présence de comptes en rapport avec l'université
- les nombreux tableaux du compte de la bibliothèque universitaire de Rennes 1, qui utilise Pinterest comme outil de curation des nouveaux ouvrages.
<h3>Les épingles</h3>
<h4>Text-mining des descriptions des épingles  :</h4>
<h4><a href="http://dev.data-bzh.fr/wp-content/uploads/2016/08/wordcloud-pinterest-2.jpeg"><img class="aligncenter size-full wp-image-1383" src="http://dev.data-bzh.fr/wp-content/uploads/2016/08/wordcloud-pinterest-2.jpeg" alt="Nuage de mots des mots les plus fréquents" width="600" height="600" /></a></h4>
<h4><a href="http://dev.data-bzh.fr/wp-content/uploads/2016/08/mots-frequents-notes-pins-2.jpeg"><img class="aligncenter size-full wp-image-1382" src="http://dev.data-bzh.fr/wp-content/uploads/2016/08/mots-frequents-notes-pins-2.jpeg" alt="Mots les plus fréquents dans les descriptions" width="1200" height="600" /></a>Les couleurs les plus utilisées sur les épingles sont :</h4>
<a href="http://dev.data-bzh.fr/wp-content/uploads/2016/08/couleurs-frequentes-2.jpeg"><img class="aligncenter size-full wp-image-1368" src="http://dev.data-bzh.fr/wp-content/uploads/2016/08/couleurs-frequentes-2.jpeg" alt="Couleurs pinterest" width="1200" height="600" /></a>

Dans la globalité, les couleurs des épingles oscillent autour des tonalités bleues et grises.
<h4>Liens les plus fréquents :</h4>
<a href="http://dev.data-bzh.fr/wp-content/uploads/2016/08/liens-frequents-2.jpeg"><img class="aligncenter size-full wp-image-1369" src="http://dev.data-bzh.fr/wp-content/uploads/2016/08/liens-frequents-2.jpeg" alt="liens les plus fréquents" width="1200" height="600" /></a>Nous constatons qu'une <strong>large majorité des épingles ne renvoient aucun lien</strong> — ce sont donc des pins qui ont été directement uploadés sur le réseau social par les utilisateurs. Ici, rennesacoupdecoeur.fr est une source importante d'épingles si l'on s'en tient à la globalité des épingles ; cependant, sur tous les pins qui renvoient à ce site, seulement 4 n'ont pas été publiées par le compte Pinterest du blog.
<h3>Âge des tableaux et volume d'épingles</h3>
<a href="http://dev.data-bzh.fr/wp-content/uploads/2016/08/age-tableaux-epingles-2.jpeg"><img class="aligncenter size-full wp-image-1373" src="http://dev.data-bzh.fr/wp-content/uploads/2016/08/age-tableaux-epingles-2.jpeg" alt="Volume d'épingles en fonction de l'âge du tableau" width="1200" height="600" /></a>

Ici, une tendance qui correspond à celle que nous aurions intuitivement formulée : <strong>les tableaux les plus vieux comptent plus d'épingles que les tableaux récents</strong> — celui qui affiche le plus de pins fait d'ailleurs partie du "trio de tête des anciens". Malgré cela, les tableaux récents contiennent un volume d'épingles plus élevé que les individus autour de la moyenne d'âge.

Retrouvez le code R utilisé ici sur notre <a href="https://github.com/DataBzh/social-media/blob/master/datamining-rennes-pinterest" target="_blank">compte GitHub</a> !