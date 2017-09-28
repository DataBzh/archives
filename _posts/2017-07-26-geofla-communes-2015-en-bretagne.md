---
ID: 3609
post_title: 'Geofla® &#8211; Communes 2015 en Bretagne'
author: Colin FAY
post_excerpt: ""
layout: post
permalink: >
  http://data-bzh.fr/geofla-communes-2015-en-bretagne/
published: true
post_date: 2017-07-26 14:00:10
---
<h2>Court aperçu de la Bretagne administrative vue par la base Geofla</h2>
<!--more-->
<h3>À propos des données</h3>
Nous avons téléchargé ce jeu de données sur la plateforme dataNOVA — <a href="https://datanova.legroupe.laposte.fr/explore/dataset/geoflar-communes-2015/table/" target="_blank" rel="noopener noreferrer">Geofla® - Communes 2015</a>.

[Tweet "#DataViz — La population de #Bretagne vue par Geofla"]
<h3>Communes par département</h3>
<a href="http://data-bzh.fr/wp-content/uploads/2017/07/communes-bretagne.png"><img class="aligncenter size-full wp-image-3610" src="http://data-bzh.fr/wp-content/uploads/2017/07/communes-bretagne.png" alt="" width="1200" height="600" /></a>Au total, notre jeu de données affiche 1270 communes en Bretagne administrative, qui se découpent ainsi : 373 communes dans les Côtes d'Armor, 283 dans le Finistère, 353 en Ille-et-Vilaine, et 261 dans le Morbihan.
<h3>Typologie des communes</h3>
<a href="http://data-bzh.fr/wp-content/uploads/2017/07/typologie-communes-bretagne.png"><img class="aligncenter size-full wp-image-3620" src="http://data-bzh.fr/wp-content/uploads/2017/07/typologie-communes-bretagne.png" alt="" width="1200" height="600" /></a>

Sans surprise, l'immense majorité des communes du département sont des communes simples.
<h3>Superficie des communes</h3>
Quelle est la superficie moyenne des villes de chaque département ?

<img class="aligncenter size-full wp-image-3626" src="http://data-bzh.fr/wp-content/uploads/2017/07/superficie-departement.png" alt="" width="1200" height="600" />

Voici les chiffres clés de la superficie des villes bretonnes :
<pre id="rstudio_console_output" class="GNKRCKGCFSB" tabindex="0"><span class="GNKRCKGCFSB">|NOM_DEPT        | Superficie_moyenne| Superficie_médiane| Ecart_type|
|:---------------|------------------:|------------------:|----------:|
|COTES-D'ARMOR   |           18722.17|              15680|   13295.97|
|FINISTERE       |           23888.41|              19050|   17520.65|
|ILLE-ET-VILAINE |           19354.16|              15510|   14255.40|
|MORBIHAN        |           26178.01|              22020|   18848.41|</span></pre>
Ici, ce sont les villes du Morbihan qui affichent la plus grande superficie moyenne et médiane.  Si nous nous représentons les superficies sous forme d'histogrammes :

<a href="http://data-bzh.fr/wp-content/uploads/2017/07/hist-superficie-communes-bret.png"><img class="aligncenter size-full wp-image-3612" src="http://data-bzh.fr/wp-content/uploads/2017/07/hist-superficie-communes-bret.png" alt="" width="1200" height="600" /></a>

Les quinze villes les plus grandes sont :

<a href="http://data-bzh.fr/wp-content/uploads/2017/07/barplot-villes-peuplees.png"><img class="aligncenter size-full wp-image-3618" src="http://data-bzh.fr/wp-content/uploads/2017/07/barplot-villes-peuplees.png" alt="" width="1200" height="600" /></a>
<pre id="rstudio_console_output" class="GNKRCKGCFSB" tabindex="0"><span class="GNKRCKGCFSB">|NOM_COM          | SUPERFICIE|
|:----------------|----------:|
|SCAER            |     117790|
|PAIMPONT         |     110160|
|LANGUIDIC        |     105460|
|LANGONNET        |      86030|
|QUIMPER          |      84370|
|GUISCRIFF        |      84240|
|PLUVIGNER        |      82900|
|LOUDEAC          |      81950|
|PLONEVEZ-DU-FAOU |      80830|
|CROZON           |      80510|
|GLOMEL           |      79180|
|BANNALEC         |      78090|
|LAMBALLE         |      77410|
|PLOERDUT         |      76190|
|PLEYBEN          |      75870|</span></pre>
Qu'en est-il maintenant de la population ?
<h3>Population des communes</h3>
<a href="http://data-bzh.fr/wp-content/uploads/2017/07/barplot-population.png"><img class="aligncenter size-full wp-image-3627" src="http://data-bzh.fr/wp-content/uploads/2017/07/barplot-population.png" alt="" width="1200" height="600" /></a>

Chiffres clés de la population bretonnes :
<pre id="rstudio_console_output" class="GNKRCKGCFSB" tabindex="0"><span class="GNKRCKGCFSB">|NOM_DEPT        | Population_moyenne| Population_médiane| Ecart_type|
|:---------------|------------------:|------------------:|----------:|
|COTES-D'ARMOR   |           1596.598|                871|   3040.674|
|FINISTERE       |           3184.781|               1565|   9344.402|
|ILLE-ET-VILAINE |           2855.244|               1288|  11574.760|
|MORBIHAN        |           2806.023|               1526|   5403.832|</span></pre>
On constate que la population moyenne est quasi semblable en Ille-et-Vilaine et dans le Morbihan. C'est le Finistère qui affiche le plus haut taux moyen de population par ville.

<a href="http://data-bzh.fr/wp-content/uploads/2017/07/hist-population-bretonne.png"><img class="aligncenter size-full wp-image-3614" src="http://data-bzh.fr/wp-content/uploads/2017/07/hist-population-bretonne.png" alt="" width="1200" height="600" /></a>

Quelles sont les villes les plus peuplées ?

<a href="http://data-bzh.fr/wp-content/uploads/2017/07/villes-peuplees-bretagne.png"><img class="aligncenter size-full wp-image-3619" src="http://data-bzh.fr/wp-content/uploads/2017/07/villes-peuplees-bretagne.png" alt="" width="1200" height="600" /></a>
<pre id="rstudio_console_output" class="GNKRCKGCFSB" tabindex="0"><span class="GNKRCKGCFSB">NOM_COM        | POPULATION|
|:--------------|----------:|
|RENNES         |     209860|
|BREST          |     139676|
|QUIMPER        |      63360|
|LORIENT        |      57706|
|VANNES         |      52648|
|SAINT-BRIEUC   |      45936|
|SAINT-MALO     |      44620|
|LANESTER       |      22142|
|FOUGERES       |      20040|
|LANNION        |      19380|
|CONCARNEAU     |      18557|
|PLOEMEUR       |      17875|
|VITRE          |      17177|
|BRUZ           |      16670|
|CESSON-SEVIGNE |      16206|</span></pre>
<h3>Les noms de communes</h3>
<a href="http://data-bzh.fr/wp-content/uploads/2017/07/mots-recurrents-noms-commune.png"><img class="aligncenter size-full wp-image-3615" src="http://data-bzh.fr/wp-content/uploads/2017/07/mots-recurrents-noms-commune.png" alt="" width="1200" height="600" /></a>

Les quinze termes les plus fréquents sont :
<pre id="rstudio_console_output" class="GNKRCKGCFSB" tabindex="0"><span class="GNKRCKGCFSB">|mot      |   n|
|:--------|---:|
|saint    | 196|
|chapelle |  16|
|bretagne |  12|
|mer      |   9|
|ile      |   8|
|sainte   |   8|
|jean     |   7|
|pont     |   7|
|noyal    |   6|
|rance    |   6|
|cogles   |   5|
|couesnon |   5|
|gilles   |   5|
|grand    |   5|
|landes   |   5|</span></pre>
Ici, une forte place à des termes bien connus des habitants bretons : saint, chapelle, Bretagne, île... une thématique représentative de la culture régionale, qui se reflète bien dans les noms des villes.

Le code sur notre <a href="https://github.com/DataBzh/territoire">Github</a>.