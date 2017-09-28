---
ID: 874
post_title: '#DataMining — Rennes Métropole sur Facebook'
author: Colin FAY
post_excerpt: ""
layout: post
permalink: >
  http://data-bzh.fr/datamining-rennes-metropole-facebook/
published: true
post_date: 2016-05-23 18:00:12
---
<h2>Dans ce billet, nous explorons la page Facebook de Rennes Metropole.</h2>
<!--more-->
<h3>Rennes Métropole : carte d'identité</h3>
Ces données ont été collectées le 19 mai à 21h. À cette date,<a href="https://www.facebook.com/metropole.rennes/" target="_blank"> Rennes Métropole</a> affiche <strong>24 907 fans</strong>, et <strong>3 602 checkins</strong>. L'API du réseau social nous permet de remonter <strong>1561 publications</strong> (jusqu'au 28 février 2014), dont 957 publiées par la page — le reste étant des contenus de visiteurs.
<p style="text-align: right;"><em>Si vous souhaitez zoomer sur les visualisations, merci de cliquer sur les images.</em></p>

<h3>Les publications sur le mur</h3>
<h4>Volumétrie mensuelle</h4>
<a href="http://dev.data-bzh.fr/wp-content/uploads/2016/05/volume-mensuel-publications-2.jpeg" rel="attachment wp-att-886"><img class="aligncenter size-full wp-image-886" src="http://dev.data-bzh.fr/wp-content/uploads/2016/05/volume-mensuel-publications-2.jpeg" alt="Volume de publications par mois" width="1200" height="600" /></a>

Entre 2014 et 2016, le nombre de publications par mois fluctue, avec <strong>une augmentation par vague</strong>. Nous constatons un pic en mai 2015, ainsi qu'en mars et avril 2016. Deux périodes de calme se dégagent : de février à avril 2015, et en juin juillet de cette même année. La baisse affichée en mai 2016 est liée à la date de collecte, faite à la moitié du mois.
<h4>Par type de publications</h4>
Au total, sur ces 1561 publications, nous trouvons :

- Sur l'ensemble des données :
68 événements, 621 liens, 1 note, 585 photos, 169 statuts et 117 vidéos.
- Publiées par la page Facebook :
32 événements, 369 liens, 1 note, 458 photos, 16 statuts et 81 vidéos.
- Publiées par les visiteurs :
36 événements, 252 liens, 127 photos, 153 statuts et 36 vidéos.

<a href="http://dev.data-bzh.fr/wp-content/uploads/2016/05/type-publication-page-facebook-2.jpeg" rel="attachment wp-att-875"><img class="aligncenter size-full wp-image-875" src="http://dev.data-bzh.fr/wp-content/uploads/2016/05/type-publication-page-facebook-2.jpeg" alt="Types de contenus sur la page facebook de Rennes Metropole" width="1200" height="600" /></a>Sur la page Facebook de Rennes Métropole, <strong>les visiteurs publient majoritairement des liens</strong>. La page, quant à elle, poste plus de photos que de liens. Les statuts sur la page sont pour la plupart du fait des visiteurs, la page n'en publiant que très peu.
<h4>Volume d'interactions par type de publication</h4>
<a href="http://dev.data-bzh.fr/wp-content/uploads/2016/05/interaction-type-publications-2.jpeg" rel="attachment wp-att-887"><img class="aligncenter size-full wp-image-887" src="http://dev.data-bzh.fr/wp-content/uploads/2016/05/interaction-type-publications-2.jpeg" alt="Interactions par type de publications" width="1200" height="600" /></a>Nous remarquons que la répartition du volume d'interactions par type de publications est semblable à la répartition du volume de publications par la page. Nous pouvons en déduire que <strong>les publications des visiteurs ont peu de poids dans les interactions</strong> globales : au total, il y a eu plus de liens que de photos, avec une large part postée par les visiteurs — pourtant, ce sont les photos qui comptent le plus d'interactions.
<h4>Par type d'interaction</h4>
En moyenne, <strong>les publications par la page Facebook reçoivent 114,37 interactions</strong> — 89 likes, 3,6 commentaires et 21,5 partages. Les posts des visiteurs, quant à eux, affichent une moyenne de 8,27 interactions — 6 likes, 0,3 commentaire et 1,9 partage.

Nous constatons que la volumétrie des likes, des commentaires et des partages est très liée. Un phénomène dû à la popularité en "effet boule de neige", sur le réseau : la visibilité d'un post influe sur les interactions, qui en retour influe sur la visibilité du contenu.

<a href="http://dev.data-bzh.fr/wp-content/uploads/2016/05/com-likes-shares-2.jpeg" rel="attachment wp-att-947"><img class="aligncenter size-full wp-image-947" src="http://dev.data-bzh.fr/wp-content/uploads/2016/05/com-likes-shares-2.jpeg" alt="Commentaires, likes et partages sur la page Facebook de Rennes Metropole" width="1200" height="600" /></a>

La publication affichant <strong>le plus d'interactions dans notre jeu de données date du 08 décembre 2015</strong> — il s'agit d'un lien vers une page du site de Unidivers, avec 7117 interactions : 1550 partages, 233 commentaires et 5334 likes. Il s'agit de la publication la plus likée, la plus commentée et la plus partagée.

<a href="http://dev.data-bzh.fr/wp-content/uploads/2016/05/repartition-interactions-type-publications-2.jpeg" rel="attachment wp-att-888"><img class="aligncenter size-full wp-image-888" src="http://dev.data-bzh.fr/wp-content/uploads/2016/05/repartition-interactions-type-publications-2.jpeg" alt="Répartition des interactions en fonction du type de publication" width="1200" height="600" /></a>Quel que soit le type de publication,<strong> les likes représentent systématiquement plus de la moitié des interactions</strong>. La proportion de commentaires sur le type note est significativement plus importante que pour le reste des posts — cependant, il n'y a qu'une seule occurrence de ce format dans notre jeu de données, n'en faisant pas un échantillon représentatif. Les événements sont très peu partagés, là où les vidéos sont les contenus qui le sont le plus.
<h4>Volume d'interactions sur les publications</h4>
<a href="http://dev.data-bzh.fr/wp-content/uploads/2016/05/interaction-type-publication-2.jpeg" rel="attachment wp-att-884"><img class="aligncenter size-full wp-image-884" src="http://dev.data-bzh.fr/wp-content/uploads/2016/05/interaction-type-publication-2.jpeg" alt="Volume d'interactions par type de publication" width="1200" height="600" /></a>

Afin d'améliorer la lisibilité de cette visualisation, nous avons posé les limites suivantes : en x, 50 interactions, en y, 500 occurrences.

Sur les chiffres que l'on ne voit pas ici : seulement<strong> 313 des 1561 publications</strong> étudiées ici <strong>comptent plus de 50 interaction</strong>s (commentaires, likes et partages combinés). 322 publications n'ont reçu aucun like, 981 n'ont pas été commentés et 698 jamais partagés —<strong> ainsi, plus de la moitié des contenus ne sont jamais commentés</strong>, <strong>un sur cinq ne compte aucun "j'aime"</strong>, et <strong>un peu moins de la moitié ne sont jamais partagés</strong>.
<h4>Text-mining des publications par la page</h4>
<a href="http://dev.data-bzh.fr/wp-content/uploads/2016/05/mots-utilises-page-2.jpeg" rel="attachment wp-att-962"><img class="aligncenter size-full wp-image-962" src="http://dev.data-bzh.fr/wp-content/uploads/2016/05/mots-utilises-page-2.jpeg" alt="Mots les plus utilisés par la page" width="1200" height="600" /></a>Parmi les mots les plus utilisés, des<strong> déictiques spatiaux et temporels</strong> : les jours de la semaine, les mois, "demain", "prochain", "aujourd'hui", etc., ainsi que des lieux physique — "place", "expo", "Thabor"... Une famille accompagné du champ lexical du rendez-vous et de l'événementiel — "loisir", "culture", "sport", "festival", "festivités", "rendez-vous"... Cette combinaison est typique des pages des villes, plateformes utilisées pour créer du lien entre les citoyens et la ville au travers de la promotion des événements culturels de la métropole.

Nous retrouvons aussi un autre réseau social, appartenant également à Facebook : Instagram.<a href="http://dev.data-bzh.fr/wp-content/uploads/2016/05/wordcloud-publications-page-2.jpeg" rel="attachment wp-att-963"><img class="aligncenter size-full wp-image-963" src="http://dev.data-bzh.fr/wp-content/uploads/2016/05/wordcloud-publications-page-2.jpeg" alt="Nuage de mots des publications" width="600" height="600" /></a>

&nbsp;
<h3>Qui interagit le plus ?</h3>
<h4>Les commentaires</h4>
Au total, sur les 3647 commentaires laissés sur les contenus étudiés ici, nous retrouvons <strong>2332 internautes différents</strong>. L'immense majorité n’ont laissé qu'<strong>un commentaire sous les publications sur la page</strong> — seulement 460 internautes comptent deux commentaires ou plus.

<a href="http://dev.data-bzh.fr/wp-content/uploads/2016/05/volume-commentaires-par-internautes-2.jpeg" rel="attachment wp-att-956"><img class="aligncenter size-full wp-image-956" src="http://dev.data-bzh.fr/wp-content/uploads/2016/05/volume-commentaires-par-internautes-2.jpeg" alt="Nombre de commentaires par internautes sur la page Facebook de Rennes Métropole" width="1200" height="600" /></a>
<h5>Les 10 comptes qui ont le plus commenté</h5>
<a href="http://dev.data-bzh.fr/wp-content/uploads/2016/05/internautes-commentaires-facebook-rennes-2.jpeg" rel="attachment wp-att-882"><img class="aligncenter size-full wp-image-882" src="http://dev.data-bzh.fr/wp-content/uploads/2016/05/internautes-commentaires-facebook-rennes-2.jpeg" alt="Qui sont les internautes qui ont le plus commenté sur la page Facebook de Rennes Métropole ?" width="1200" height="600" /></a>

Sans surprise,<strong> Rennes Metropole est le profil qui a le plus commenté</strong> sur les publications, avec 44 unités.
<h5>Text-mining des commentaires</h5>
<a href="http://dev.data-bzh.fr/wp-content/uploads/2016/05/mots-utilises-commentaires-2.jpeg" rel="attachment wp-att-942"><img class="aligncenter size-full wp-image-942" src="http://dev.data-bzh.fr/wp-content/uploads/2016/05/mots-utilises-commentaires-2.jpeg" alt="Les 20 mots les plus utilisés dans les commentaires" width="1200" height="600" /></a>Sur l'ensemble des commentaires laissés sur les publications de la page Facebook, <strong>les mots les plus utilisés sont majoritairement positifs</strong> — après "ville" (206 occurrences) et "plus" (174 oc.) tous les deux neutres, nous retrouvons "bien" (157 oc.), "magnifique" (113 oc.), "beau" (108 oc.), "merci" (107 oc.), "super" (88 oc.) et "belle" (79 oc.).

Dans le nuage des mots les plus utilisés, nous retrouvons le champ lexical de l'événement ("soirée", "spectacle", "culture"...), ainsi que celui de la vie locale ("quartier", "régional", "artisans", "travaux", "maison"...). Nous trouvons également une référence à une autre ville : Nantes.

<a href="http://dev.data-bzh.fr/wp-content/uploads/2016/05/wordcloud-commentaire-facebook-2.jpeg" rel="attachment wp-att-885"><img class="aligncenter size-full wp-image-885" src="http://dev.data-bzh.fr/wp-content/uploads/2016/05/wordcloud-commentaire-facebook-2.jpeg" alt="Nuage de mots des commentaires sur la page Facebook de Rennes Metropole" width="600" height="600" /></a>
<h4>Les Likes</h4>
Avec un total de 89 051, les posts reçoivent en moyenne 57 likes. 22 257 internautes ont mis un "J'aime" ou plus sur une publication sur la page Facebook de Rennes Metropole (page et visiteurs compris) — <strong>l'internaute qui affiche le plus de likes en compte 259</strong>.

<a href="http://dev.data-bzh.fr/wp-content/uploads/2016/05/internautes-like-facebook-rennes-metropole-2.jpeg" rel="attachment wp-att-883"><img class="aligncenter size-full wp-image-883" src="http://dev.data-bzh.fr/wp-content/uploads/2016/05/internautes-like-facebook-rennes-metropole-2.jpeg" alt="Internautes ayant liké le plus de publications sur la page facebook de Rennes Metropole" width="1200" height="600" /></a>
<h3>Exploration de l'environnement</h3>
<h4>À propos de la collecte de ces données</h4>
Chaque page Facebook peut aimer d'autres pages du réseau, pour afficher son lien. Afin de collecter les relations dans l'environnement de Rennes Métropole, nous avons <strong>lancé une requête sur les 25 dernières pages aimées</strong> par la ville bretonne, puis sur les résultats, et une nouvelle fois sur ces résultats. Au total, nous avons bouclé cette requête sur 3 niveaux, et<strong> notre script a renvoyé 5164 pages Facebook</strong> — certaines présentes sur plusieurs niveaux et/ou dans les résultats de plusieurs pages.
<h4>Carte d'identité de l'environnement</h4>
Sur ces trois niveaux, les pages <strong>affichent en moyenne 283 483,5 fans</strong>. Le profil le plus présent sur ces trois niveaux est Rennes Métropole (13 fois). Viennent ensuite Rue des Livres (11 fois) et l'Association Electroni[K] (11 fois).

<a href="http://dev.data-bzh.fr/wp-content/uploads/2016/05/pages-aimees-3-niveaux-2.jpeg" rel="attachment wp-att-912"><img class="aligncenter size-full wp-image-912" src="http://dev.data-bzh.fr/wp-content/uploads/2016/05/pages-aimees-3-niveaux-2.jpeg" alt="Pages aimées sur trois niveaux" width="1200" height="600" /></a>
<h4>Catégories des pages de l'environnement</h4>
<h4><a href="http://dev.data-bzh.fr/wp-content/uploads/2016/05/categories-pages-2.jpeg" rel="attachment wp-att-913"><img class="aligncenter wp-image-913 size-full" src="http://dev.data-bzh.fr/wp-content/uploads/2016/05/categories-pages-2.jpeg" alt="Catégories des pages de l'environnement" width="1200" height="600" /></a></h4>
Sur ces trois niveaux, les pages appartiennent à <strong>159 catégories différentes</strong> — la plus représentée étant <strong>Musician/Band</strong>. Viennent ensuite Community et Non-Profit Organization. 77 catégories comptent 10 pages ou plus.
<h4>Origine géographique des pages</h4>
<a href="http://dev.data-bzh.fr/wp-content/uploads/2016/05/origine-geo-pages-2.jpeg" rel="attachment wp-att-916"><img class="aligncenter size-full wp-image-916" src="http://dev.data-bzh.fr/wp-content/uploads/2016/05/origine-geo-pages-2.jpeg" alt="Origine géographique des pages" width="1200" height="600" /></a>La ville la plus représentée dans cette suite est Rennes, avec 435 occurrences. Viennent ensuite Paris, avec 373 occurrences, et Nantes, avec 71 pages.
<h3>À propos de ces données</h3>
Ces données ont été<strong> collectées, traitées et visualisées avec R</strong>, via des <strong>requêtes API réalisées par nos soins</strong>. Vous souhaitez en savoir plus sur ces résultats, ou les scripts rédigés pour les obtenir ? <a href="mailto:contact@data-bzh.fr">Contactez-nous</a> !