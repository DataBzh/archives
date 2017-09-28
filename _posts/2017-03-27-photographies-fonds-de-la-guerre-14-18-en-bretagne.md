---
ID: 2516
post_title: 'Photographies : Fonds de la guerre 14-18 en Bretagne'
author: Colin FAY
post_excerpt: ""
layout: post
permalink: >
  http://data-bzh.fr/photographies-fonds-de-la-guerre-14-18-en-bretagne/
published: true
post_date: 2017-03-27 14:00:20
---
<h2>Parcours de la base de données photographiques de la guerre 14-18, rendue publique par le Ministère de la Culture et de la Communication.</h2>
<!--more-->
<h3>À propos de ces photos</h3>
Voici la description donnée par le Ministère de cette collection de photos :

<em>"Ces photographies ont été réalisées à des fins de propagande et de documentation par les services français --notamment la Section photographique et cinématographique des armées à partir de 1917-- ou par les services alliés (Portugal, Italie). Elles montrent l’effort de guerre, les dégâts causés par les combats aux monuments historiques, l'évacuation des œuvres d'art, la situation à l’arrière du front (vie des civils, camps d’internement, de prisonniers, hôpitaux ou des militaires -théâtre aux armées) ..."</em>
<h3>Aperçu du jeu de données</h3>
Le dataset, intitulé <a href="https://data.culturecommunication.gouv.fr/explore/dataset/fonds-de-la-guerre-14-18-extrait-de-la-base-memoire/" target="_blank">Photographies : Fonds de la guerre 14-18</a>, est disponible sur le site d'Open Data du Ministère de la Culture et de la Communication. Une fois téléchargé, il contient 7840 entrées photographiques, avec leur lien. En filtrant sur la Bretagne, nous comptons<strong> une base de 282 photos</strong>.

<img class="aligncenter size-full wp-image-2550" src="http://data-bzh.fr/wp-content/uploads/2017/03/fond-de-guerre-1-2.jpg" alt="" width="700" height="300" />

Ces photos se répartissent, par département :

<a href="http://data-bzh.fr/wp-content/uploads/2017/03/photos-par-dep.png"><img class="aligncenter size-full wp-image-2969" src="http://data-bzh.fr/wp-content/uploads/2017/03/photos-par-dep.png" alt="" width="1200" height="600" /></a>

Ici, une<strong> forte place pour le Morbihan</strong>, qui occupe presque la moitié de notre jeu de données (113 des 282 photos). Vient ensuite l'Ille-et-Vilaine, comptant pour 93 des 282 photos. Très peu de clichés ont été pris dans les Côtes d'Armor.

Visualisons les villes d'origine des photos sur une carte :

<a href="http://data-bzh.fr/wp-content/uploads/2017/03/photos-par-ville-2.jpeg"><img class="aligncenter size-full wp-image-2518" src="http://data-bzh.fr/wp-content/uploads/2017/03/photos-par-ville-2.jpeg" alt="carte des photos" width="1200" height="600" /></a>

Rennes, avec 75 unités, compte pour le plus grand volume de photos — seulement deux autres villes d'Ille-et-Vilaine ont été photographiées.
<h3>Topologie de la bibliothèque par série</h3>
Les photos sont classées par séries. Quelle répartition pour ces étiquetages ?

<a href="http://data-bzh.fr/wp-content/uploads/2017/03/photos-series.png"><img class="aligncenter size-full wp-image-2971" src="http://data-bzh.fr/wp-content/uploads/2017/03/photos-series.png" alt="" width="1200" height="600" /></a>

Presque sans surprise, nous retrouvons une large proportion de photo issues d'une série sur les prisonniers.

<img class="aligncenter size-full wp-image-2563" src="http://data-bzh.fr/wp-content/uploads/2017/03/fonds-de-guerre-prisonniers-2.jpg" alt="" width="700" height="300" />
<h3>Topologie des lieux</h3>
Le jeu de données contient une entrée EDIF, regroupant les édifices / lieux de capture des clichés. Comment se répartissent-ils ?

<a href="http://data-bzh.fr/wp-content/uploads/2017/03/topo-lieux.png"><img class="aligncenter wp-image-2972 size-full" src="http://data-bzh.fr/wp-content/uploads/2017/03/topo-lieux.png" alt="topologie des lieux" width="1200" height="600" /></a>

Dans ces séries de photos de Bretagne, les lieux les plus représentés sont <strong>l'École Nationale d'Agriculture et l'Hopital Militaire — tous les deux situés en Ille-et-Vilaine</strong>.

Pourquoi cette forte présence de l'École Nationale de Rennes ? Il s'agit d'un lieu important de la vie civile durant la guerre — cet établissement a été transformé en <strong>centre de rééducation des mutilés de guerre</strong> : les anciens combattant y apprenant les métiers de l'agriculture équipés de prothèses et d'outils spécifiques. Nous pouvons supposer que, les clichés étant réalisés à des fins de propagande militaire, ce lieu de réadaptation des blessés de guerre a reçue une forte attention durant cette période.
<h3>Identifier les images</h3>
Pour parcourir cette bibliothèque, nous allons interroger l'API Computer Vision de Microsoft — une solution basée sur le deep learning qui vous permet d'étiqueter des photos.

Mais avant, aperçu via les légendes du jeu de données d'origine.
<h4>Unigrammes des légendes</h4>
Quels sont les mots les plus présents dans les légendes de ces photos ?

<a href="http://data-bzh.fr/wp-content/uploads/2017/03/unigram-legendes.png"><img class="aligncenter wp-image-2973 size-full" src="http://data-bzh.fr/wp-content/uploads/2017/03/unigram-legendes.png" alt="" width="1200" height="600" /></a>
<h4>Bigrammes des légendes</h4>
Même question, avec des couples de mots !
<h4><a href="http://data-bzh.fr/wp-content/uploads/2017/03/bigram-legend.png"><img class="aligncenter wp-image-2974 size-full" src="http://data-bzh.fr/wp-content/uploads/2017/03/bigram-legend.png" alt="Bigram des légendes" width="1200" height="600" /></a></h4>
Peu de surprises dans les légendes des photos, tant sur les unigrammes que sur les bigrammes — "camps", "internés", "civil", "officiers prisonniers", "officiers allemand"...  nous retrouvons un <strong>parallèle entre ces légendes et la série de photos la plus peuplées</strong> (pour rappel : Prisonniers).
<h4>Carte des légendes</h4>
Quelle représentation des légendes sur le territoire ?

<a href="http://data-bzh.fr/wp-content/uploads/2017/03/legendes-cartes.png"><img class="alignnone wp-image-2975 size-full" src="http://data-bzh.fr/wp-content/uploads/2017/03/legendes-cartes.png" alt="Mots par villes" width="1200" height="600" /></a>

&nbsp;

À <strong>Rennes</strong>, ville la plus représentée, le mot le plus présent est "mutilés". Une présence forte qui peut s'expliquer par la <strong>présence d'un camp de rééducation</strong> pour mutilés de guerre dans la capitale bretonne... à l'École Nationale d'Agriculture !
<h4><a href="http://dev.data-bzh.fr/wp-content/uploads/2017/03/camps-mutile-rennes-2.jpg"><img class="aligncenter size-full wp-image-2564" src="http://dev.data-bzh.fr/wp-content/uploads/2017/03/camps-mutile-rennes-2.jpg" alt="Rennes" width="700" height="300" /></a></h4>
<h4></h4>
<h4>Microsoft Computer Vision</h4>
Quel résultat si l'on passe ces photos dans l'API Microsoft Computer Vision ?

<em>NB : l'API renvoyant de l'information en anglais, les labels suivants sont dans cette langue.</em>

<a href="http://data-bzh.fr/wp-content/uploads/2017/03/microsoft-computer-vision-tags.png"><img class="aligncenter size-full wp-image-2976" src="http://data-bzh.fr/wp-content/uploads/2017/03/microsoft-computer-vision-tags.png" alt="Tags microsoft vision" width="1200" height="600" /></a>

Ce qui donne, sur une carte

<a href="http://data-bzh.fr/wp-content/uploads/2017/03/computer-vision-tags-villes.png"><img class="aligncenter size-full wp-image-2977" src="http://data-bzh.fr/wp-content/uploads/2017/03/computer-vision-tags-villes.png" alt="Computer Vision tags par ville" width="1200" height="600" /></a>

<em> </em>Peu de découverte si l'on se cantonne au premier mot pour chaque ville, ou au tags les plus récurrents renvoyés par l'API — beaucoup de "Photo", "Black", "White", "People"...

Alors, l'API de Microsoft est-elle vraiment capable de nous raconter automatiquement l'histoire de ces photos ? Voici 3 clichés, accompagnés de leurs légendes données par la machine :

[caption id="attachment_2553" align="aligncenter" width="700"]<a href="http://dev.data-bzh.fr/wp-content/uploads/2017/03/sap40_z0000909_p-2.jpg"><img class="wp-image-2553" src="http://dev.data-bzh.fr/wp-content/uploads/2017/03/sap40_z0000909_p-2.jpg" alt="" width="700" height="500" /></a> A group of people pose for a photo[/caption]

[caption id="attachment_2556" align="aligncenter" width="721"]<a href="http://dev.data-bzh.fr/wp-content/uploads/2017/03/sap40_d0001545a_p-2.jpg"><img class="wp-image-2556 size-full" src="http://dev.data-bzh.fr/wp-content/uploads/2017/03/sap40_d0001545a_p-2.jpg" alt="" width="721" height="512" /></a> An old photo of a kitchen[/caption]

[caption id="attachment_2557" align="aligncenter" width="724"]<a href="http://dev.data-bzh.fr/wp-content/uploads/2017/03/sap40_d0001577_p-2.jpg"><img class="wp-image-2557 size-full" src="http://dev.data-bzh.fr/wp-content/uploads/2017/03/sap40_d0001577_p-2.jpg" alt="" width="724" height="512" /></a> A group of people in a living room filled with furniture and a window.[/caption]
<p style="text-align: left;">Bref, l'API ne semble pas toujours au point... peut mieux faire ? La première photo de ce triptyque montre une <strong>légende relativement pertinente</strong> (un groupe de personne posant pour une photo). La seconde est <b>totalement à côté de la vérité </b>(ou alors, il s'agit d'une bien étrange cuisine...), et la <strong>troisième semble être la seule bien légendée</strong>.</p>
<p style="text-align: left;">Cependant, et pour la défense de la machine, la qualité des photos n'est peut-être pas assez bonne pour être un traitement de la meilleure manière : la liste des urls dans le jeu de données d'origine renvoit les vignettes de ces clichés.</p>
<p style="text-align: left;">Pour conclure, la <strong>pertinence maximale de l'étiquetage penche du côté de la description manuelle</strong>. Toujours est-il qu'avec la machine, elle reste beaucoup plus rapide !</p>