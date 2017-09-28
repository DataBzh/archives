---
ID: 1028
post_title: >
  rgeoapi — Les données géographiques
  avec R
author: Colin FAY
post_excerpt: ""
layout: post
permalink: >
  http://data-bzh.fr/donnees-geographiques-rgeoapi/
published: true
post_date: 2016-06-06 18:00:32
---
<h2>Envie de connaître l'emplacement exact de votre ville bretonne favorite ? Vous souhaitez découvrir combien de villes en France contiennent "Rennes" dans leur nom, ou encore la superficie moyenne des villes du Morbihan ? Alors, rgeoapi est fait pour vous !</h2>
<!--more-->
<h3>rgeoapi, qu'est-ce que c'est ?</h3>
Package R, <a href="https://github.com/ColinFay/rgeoapi">rgeoapi</a> vous permet de faire des requêtes sur l'API Open Data GéoAPI, par Code Postal, Code INSEE ou par nom. Les fonctions du package vous retournent un dataframe contenant le(s) nom(s) de la ou des villes, le ou les codes INSEE correspondant, le ou les codes postaux, la surface, ainsi que la longitude et la latitude des communes demandées.

Un exemple ? La requête
<p style="padding-left: 30px;"><em>&gt; getByPC(35000)</em></p>
Vous renverra :
<p style="padding-left: 30px;"><em>    name codeInsee codesPostaux surface      lat      long</em>
<em>1 Rennes     35238        35200    5035 48.11023 -1.678872</em>
<em>2 Rennes     35238        35700    5035 48.11023 -1.678872</em>
<em>3 Rennes     35238        35000    5035 48.11023 -1.678872</em></p>
Et pour répondre à la question en introduction, nous pouvons utiliser la requête
<p style="padding-left: 30px;"><em>&gt; getByName("Rennes")</em></p>
pour découvrir que 7 codes postaux renvoient à des villes contenant le mot "Rennes" :
<p style="padding-left: 30px;"><em>                   name            codeInsee codesPostaux surface      lat       long</em>
<em>1                Rennes                  35238        35200    5035 48.11023 -1.6788723</em>
<em>2                Rennes                 35238        35700    5035 48.11023 -1.6788723</em>
<em>3                Rennes                 35238       35000    5035 48.11023 -1.6788723</em>
<em>4     Rennes-le-Château      11309        11190    1497 42.91498  2.2774065</em>
<em>5      Rennes-les-Bains        11310         11190    1975 42.92166  2.3408405</em>
<em>6       Rennes-sur-Loue       25488        25440     547 47.01497  5.8551652</em>
<em>7 Rennes-en-Grenouilles   53189        53110     801 48.49128 -0.5083472</em></p>

<h3>Installer rgeoapi</h3>
Pour installer le package depuis Github, il vous suffit d'entrer la commande suivante dans votre session R :
<p style="padding-left: 30px;"><em>&gt; devtools::install_github("ColinFay/rgeoapi")</em></p>

<h3>rgeoapi, et la Bretagne en Open Data</h3>
L'objectif de ce package ? Faciliter l'accès aux données géographiques pour la construction de cartes dans R — avec rgeoapi, vous pouvez disposer de l'emplacement exact d'une ville sur la carte, ainsi que sa superficie.

Pour vous simplifier la tâche sur les données bretonnes, nous avons compilé les données disponibles pour les quatre départements de la Bretagne administrative. Dans ces fichiers, disponibles au format CSV, vous trouverez toutes les informations disponibles via les codes postaux des villes de ces départements :
<ul>
 	<li>Les <a href="http://data-bzh.fr/cotes-darmor-geo-api/" target="_blank">Côtes d'Amor par GéoAPI</a></li>
 	<li>Le <a href="http://data-bzh.fr/finistere-geo-api/" target="_blank">Finistère par GéoAPI</a></li>
 	<li>L'<a href="http://data-bzh.fr/ille-vilaine-geo-api/" target="_blank">Ille-et-Vilaine par GéoAPI</a></li>
 	<li>Le <a href="http://data-bzh.fr/morbihan-geo-api/" target="_blank">Morbihan par GéoAPI</a></li>
</ul>
Envie d'en savoir plus sur ce package ? <a href="mailto:contact@colinfay.me" target="_blank">Contactez nous</a> !