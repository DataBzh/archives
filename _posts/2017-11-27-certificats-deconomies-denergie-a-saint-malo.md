---
ID: 3827
post_title: 'Certificats d&rsquo;économies d&rsquo;énergie à Saint-Malo'
author: Colin FAY
post_excerpt: ""
layout: post
permalink: >
  http://data-bzh.fr/certificats-deconomies-denergie-a-saint-malo/
published: true
post_date: 2017-11-27 14:15:03
---
<h2>Parcours de la base de données des certificats d'économies d'énergie de Saint-Malo.</h2>
<!--more-->
<h3>À propos du jeu de données</h3>
Le jeu de données est disponible sur le site d'Open Data de Saint-Malo : <a href="https://data.stmalo-agglomeration.fr/explore/dataset/certificats-deconomies-denergie/?disjunctive.numero_operation_standardisee&amp;disjunctive.type_d_operations&amp;disjunctive.statut&amp;sort=-annee">Certificats d'économies d'énergie</a>.

On y retrouve la<strong> liste des opérations standardisées sur le patrimoine de la Ville de Saint-Malo, ayant fait l'objet d'un certificat d'économie d'énergie (CEE)</strong>. Ces certificats sont attribués aux particuliers, entreprises ou collectivités réalisant des travaux d'économies d'énergies qui sont rachetés sous formes <strong>d'offres de services ou de primes par les fournisseurs d'énergie</strong>.  Dans notre dataset, toutes les observations correspondent à de la vente de CEE.

[Tweet "#OpenData #SaintMalo — Certificats d'économie d'Énergie (données via @OdataMalo)"]

Au total, notre jeu de données compte 68 observations.
<h3 class="row ng-scope"> Certificats par an</h3>
| Année| Volume|
|-----:|------:|
| 2012| 15|
| 2013| 18|
| 2014| 15|
| 2015| 20|

Ce qui donne, en dataviz :

<a href="http://data-bzh.fr/wp-content/uploads/2017/11/cee-saint-malo-an.png"><img class="aligncenter size-full wp-image-3828" src="http://data-bzh.fr/wp-content/uploads/2017/11/cee-saint-malo-an.png" alt="" width="1200" height="600" /></a>
<h3>Les travaux les plus effectués</h3>
Quels sont les opérations les plus effectuées entre 2012 et 2015 ?

Intéressons nous d'abord aux noms "bruts" :

|Type d'opérations | Volume|
|:-------------------------------|------:|
|Isolation d'un plancher | 11|
|Luminaires LED | 8|
|Menuiseries extérieures | 8|
|Luminaire d'éclairage extérieur | 4|
|Luminaires T5 | 3|

Essayons maintenant de caractériser plus finement ces travaux : par exemple, en regroupant "Luminaire T5" et "Luminaires d'éclairage extérieur".

Voici le <strong>graphique des termes les plus récurrents dans les descriptions des types de travaux</strong>, qui ont été racinisés :

<a href="http://data-bzh.fr/wp-content/uploads/2017/11/saint_malo_stem_type_cee.png"><img class="aligncenter size-full wp-image-3831" src="http://data-bzh.fr/wp-content/uploads/2017/11/saint_malo_stem_type_cee.png" alt="" width="1200" height="600" /></a>

Ce graphique nous permet de mieux caractériser les travaux effectués, les plus nombreux étant les travaux d'isolation, puis de luminaire.
<h3>Quel volume de kWh par an ?</h3>
| Année| kWh moyen|
|-----:|---------:|
| 2012| 291678.5|
| 2013| 281996.7|
| 2014| 753531.1|
| 2015| 138411.8|

Ce qui donne, en graphique :

<a href="http://data-bzh.fr/wp-content/uploads/2017/11/cee-saint-malo-kwh.png"><img class="aligncenter size-full wp-image-3832" src="http://data-bzh.fr/wp-content/uploads/2017/11/cee-saint-malo-kwh.png" alt="" width="1200" height="600" /></a>
<h3>Adresses des CEE</h3>
Au total, 35 adresses différentes sont trouvées dans notre dataset. Voici les adresses les plus présentes :

<a href="http://data-bzh.fr/wp-content/uploads/2017/11/adresses_cee_saint_malo.png"><img class="aligncenter size-full wp-image-3836" src="http://data-bzh.fr/wp-content/uploads/2017/11/adresses_cee_saint_malo.png" alt="" width="1200" height="600" /></a>

Le code source de ce billet sur notre <a href="https://github.com/DataBzh/territoire">GitHub</a> !

&nbsp;