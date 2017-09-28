---
ID: 732
post_title: '#DataMining — Exploration des pages Facebook de 8 villes bretonnes'
author: Colin FAY
post_excerpt: ""
layout: post
permalink: >
  http://data-bzh.fr/datamining-exploration-pages-facebook-villes-bretonnes/
published: true
post_date: 2016-05-08 18:00:50
---
<h2>Dans ce billet, nous vous proposons une exploration des pages Facebook des 8 villes les plus peuplées de Bretagne administrative.</h2>
<!--more-->
<h3>Les villes bretonnes sur Facebook</h3>
Nous avons déjà abordé le volume de fans des pages Facebook de ces villes dans notre <a href="http://data-bzh.fr/datasnack-8-villes-bretonnes-facebook/">Datasnack #8 — Les villes bretonnes sur Facebook</a>. Le présent billet ne reprendra pas ce point, mais viendra <strong>explorer des informations complémentaires que nous pouvons obtenir par data-mining</strong> de ces pages. Pourquoi 8 villes ? Comme nous le signalons dans ce datasnack, seulement <strong>8 des 10 villes les plus peuplées de Bretagne</strong> possèdent un compte Facebook : Rennes, Brest, Quimper, Lorient, Vannes, Saint-Malo, Saint-Brieuc et Lanester. À noter que nous utilisons les pages Facebook dont le lien est disponible sur les sites officiels.

Pour rappel, notre visualisation des villes bretonnes sur Facebook, en fonction de leur population et du nombre de leurs abonnés sur le réseau social :

<img class="aligncenter wp-image-655 size-full" src="http://dev.data-bzh.fr/wp-content/uploads/2016/04/ville-bretonne-sur-facebook-2.jpg" alt="Les villes bretonnes sur Facebook" width="1200" height="600" />
<h3>À propos de ces données</h3>
Les données utilisées dans ce billet ont été collectées avec R. Pour obtenir les résultats ci-dessous, nous avons <strong>compilé les 250 dernières publications</strong> de ces pages (hors messages laissés par les internautes).
<h3>Quelle page affiche le plus d'interactions ?</h3>
Combinaison du nombre de likes, de comments et de shares par pages :

<a href="http://dev.data-bzh.fr/wp-content/uploads/2016/05/volume-interactions-par-page-2.jpeg" rel="attachment wp-att-764"><img class="aligncenter size-full wp-image-764" src="http://dev.data-bzh.fr/wp-content/uploads/2016/05/volume-interactions-par-page-2.jpeg" alt="Volume des interactions sur les pages facebook des villes bretonnes" width="1200" height="600" /></a>

Nous constatons que la page affichant le plus grand nombre de fans (Rennes) n'est pas celle qui affiche le nombre d'interactions le plus important (Saint-Malo). Une tendance que nous avions déjà constaté dans notre datasnack — le nombre de "ils en parlent" n'étant pas le plus élevé sur la page avec le nombre de fans le plus important.
<h3>Quelle typologie de contenu ?</h3>
Proportion des formes de contenus sur les 250 derniers publication des pages.

<a href="http://dev.data-bzh.fr/wp-content/uploads/2016/05/typo-publications-pages-facebook-2.jpeg" rel="attachment wp-att-765"><img class="aligncenter size-full wp-image-765" src="http://dev.data-bzh.fr/wp-content/uploads/2016/05/typo-publications-pages-facebook-2.jpeg" alt="Typologie des publications sur les pages Facebook des villes bretonnes" width="1200" height="600" /></a>

Les pages Facebook des villes bretonnes publient massivement des <strong>photos, des liens et des vidéos</strong>. Toutes les pages publient au moins 3 types de contenus différents.
<h3>Le contenu impacte-t-il les interactions ?</h3>
Comme nous le voyons, les pages Facebook des villes bretonnes ne publient pas les mêmes proportions de types de publications. Cela impacterait-il les interactions ?

<a href="http://dev.data-bzh.fr/wp-content/uploads/2016/05/repartition-interaction-type-publication-2.jpeg" rel="attachment wp-att-766"><img class="aligncenter size-full wp-image-766" src="http://dev.data-bzh.fr/wp-content/uploads/2016/05/repartition-interaction-type-publication-2.jpeg" alt="Répartition des interactions par type de contenu" width="1200" height="600" /></a>

La ville de Saint-Malo et la ville de Lorient reçoivent de gros volumes d'interactions sur leurs publications de vidéo. Sur l'ensemble des pages, les événements ne reçoivent que peu (voir pas) d'interactions.

Les 3 contenus les plus likés :
- Ville de Lorient / Vidéo / 2151 likes
- Rennes Ville et Métropole / Photo / 1962 likes
- Ville de Saint-Malo / Vidéo / 1432 likes

Les 3 contenus les plus commentés :
- Ville de Lorient / Vidéo / 120 commentaires
- Rennes Ville et Métropole / Lien / 102 commentaires
- Ville de Saint-Malo / Vidéo / 61 commentaires

Les 3 contenus les plus partagés :
- Ville de Lorient / Vidéo / 14516 commentaires
- Ville de Saint-Malo / Vidéo / 888 commentaires
- Ville de Saint-Malo / Vidéo / 738 commentaires
<h3>Volume d'interactions sur un contenu</h3>
<a href="http://dev.data-bzh.fr/wp-content/uploads/2016/05/interaction-publication-2.jpeg" rel="attachment wp-att-751"><img class="aligncenter size-full wp-image-751" src="http://dev.data-bzh.fr/wp-content/uploads/2016/05/interaction-publication-2.jpeg" alt="Nombre d'interactions par publication" width="1200" height="600" /></a>Afin d'améliorer la lisibilité de cette visualisation, nous avons effectué un zoom, en créant les limites suivantes : en x, 50 interactions, en y, 500 occurrences.
Les données non-visibles ici : 408 publications ont plus de 500 likes (avec un maximum de 2151). 1086 contenus ont 0 commentaires, seulement 6 plus de 50 (avec un maximum de 120). 572 publications ont 0 partage, et 184 plus de 50 (avec un maximum de 14516).

Sur ces interactions, nous pouvons noter qu'il y a <strong>plus de publications recevant 1 like (96) que de publications n'en recevant aucun</strong> — il s'agit du seul type d'interaction connaissant cette tendance. La limite <strong>maximum de commentaires est quant à elle la plus faible des trois types</strong> d'interactions : aucune publication ne dépasse 120 commentaires, là où les likes montent à 2151 et les partages à 14516.
<h3>Type d'interaction par type de publication, toutes pages confondues</h3>
<a href="http://dev.data-bzh.fr/wp-content/uploads/2016/05/interaction-types-publication-2.jpeg" rel="attachment wp-att-754"><img class="aligncenter size-full wp-image-754" src="http://dev.data-bzh.fr/wp-content/uploads/2016/05/interaction-types-publication-2.jpeg" alt="Volume d'interactions par type de publications" width="1200" height="600" /></a>Ici, toutes pages confondues, ce sont <strong>les vidéos qui récoltent le plus d'interactions</strong>, notamment en terme de partages. Les vidéos sont d'ailleurs le seul type de contenu à recevoir plus de partage que de commentaires ou de likes. Les<strong> commentaires restent le type d'interactions le moins présent</strong> dans notre corpus.

Côté likes, ce sont les vidéos qui affichent le plus de "j'aime", ensuite les photos, puis les liens.
<h3>L'instant text-mining : de quoi parlent les pages ?</h3>
<p style="text-align: right;"><em>Notes : vous pouvez retrouver le code R utilisé ici dans notre série de billet sur le <a href="http://data-bzh.fr/text-mining-r-part-1/">text-mining avec R</a>.</em></p>
À noter que pour une lecture plus complète, nous avons<strong> retiré le nom des villes de la liste des mots à afficher</strong>.

<strong>Les dix termes les plus utilisés sur ces 8 pages : </strong>

<a href="http://dev.data-bzh.fr/wp-content/uploads/2016/05/text-mining-page-facebook-2.jpeg" rel="attachment wp-att-767"><img class="aligncenter size-full wp-image-767" src="http://dev.data-bzh.fr/wp-content/uploads/2016/05/text-mining-page-facebook-2.jpeg" alt="Text mining des pages facebook des villes bretonnes" width="1200" height="600" /></a>

Parmi les mots les plus utilisés, nous trouvons de <strong>nombreux déictiques spatiaux et temporels</strong> : samedi, avril, mars, dimanche, février... &amp; place, festival, rue, centre... Tous les jours de la semaine font partie des 100 mots les plus utilisés dans les publications.

Nous retrouvons, également dans les 100 mots les plus fréquents, des <strong>terminologies typiques de l'invitation</strong> : rendez-vous, découvrir, venez... et de l'événementiel : festival, programme, musique, animation, fête...

Cette combinaison des termes de situation et des termes de l'invitation sont typique du format de pages que nous étudions ici — il s'agit de compte Facebook de villes, des officiels qui utilisent le réseau social pour faire la promotion de leurs événements physiques.

<strong>Nuage de mot des termes les plus utilisés :</strong>

<a href="http://dev.data-bzh.fr/wp-content/uploads/2016/05/nuage-mots-pages-facebook-2.jpeg" rel="attachment wp-att-768"><img class="aligncenter size-full wp-image-768" src="http://dev.data-bzh.fr/wp-content/uploads/2016/05/nuage-mots-pages-facebook-2.jpeg" alt="Nuage de mots clés des pages facebook des villes bretonnes" width="600" height="600" /></a>

&nbsp;