---
ID: 3692
post_title: >
  Etablissements cinématographiques en
  2016
author: Colin FAY
post_excerpt: ""
layout: post
permalink: >
  http://data-bzh.fr/etablissements-cinematographiques-en-2016/
published: true
post_date: 2017-09-11 18:00:15
---
<h2>Aperçu des cinémas de Bretagne administrative en dataviz.</h2>
<!--more-->
<h3>À propos du jeu de données</h3>
&nbsp;

Le jeu de données que nous utilisons ici est disponible sur le site du Ministère de la culture : <a href="https://data.culturecommunication.gouv.fr/explore/dataset/etablissements-cinematographiques/information/">Etablissements cinématographiques en 2016</a>.

Il a était nettoyé et filtré pour ne garder que les entrées de Bretagne. Au total, le dataset compte 122 établissements.

[Tweet "#DataViz #Bretagne — Établissements cinématographiques de Bretagne"]
<h3>Établissements par département</h3>
<a href="http://data-bzh.fr/wp-content/uploads/2017/09/cine_bretagne.png"><img class="aligncenter size-full wp-image-3694" src="http://data-bzh.fr/wp-content/uploads/2017/09/cine_bretagne.png" alt="" width="1200" height="600" /></a>
<pre id="rstudio_console_output" class="GNKRCKGCFSB" tabindex="0"><span class="GNKRCKGCFSB">   Côtes d'Armor    21
       Finistère    33
 Ille-et-Vilaine    41
        Morbihan    27</span></pre>
Avec 41 cinémas, c'est l'Ille-et-Vilaine qui compte le plus d'établissements dans la région.
<h3>Villes avec le plus d'établissements</h3>
<a href="http://data-bzh.fr/wp-content/uploads/2017/09/etablissements-cine-bretagne.png"><img class="aligncenter size-full wp-image-3695" src="http://data-bzh.fr/wp-content/uploads/2017/09/etablissements-cine-bretagne.png" alt="" width="1200" height="600" /></a>

Brest et Rennes se disputent la première place avec 4 établissements chacun.
<pre id="rstudio_console_output" class="GNKRCKGCFSB" tabindex="0"><span class="GNKRCKGCFSB">                Brest      4
               Rennes      4
              Quimper      3
           Douarnenez      2
              Morlaix      2
           Saint-Malo      2
               Vannes      2
               Acigné      1
  Argentré-du-Plessis      1
                Arzon      1
</span></pre>
<h3>Mots récurrents dans les noms</h3>
<a href="http://data-bzh.fr/wp-content/uploads/2017/09/noms-cine-bretagne.png"><img class="aligncenter size-full wp-image-3696" src="http://data-bzh.fr/wp-content/uploads/2017/09/noms-cine-bretagne.png" alt="" width="1200" height="600" /></a>

Sans surprise, Ciné arrive en tête de liste. On retrouve également des noms relativement typiques du champs sémantique du cinéma : cineville, club, ou encore rex. D'un autre côté, des noms orientés Bretagne,  tels que celtic ou korrigan.
<pre id="rstudio_console_output" class="GNKRCKGCFSB" tabindex="0"><span class="GNKRCKGCFSB">       cine    12
      salle     8
     celtic     4
  cineville     4
       club     4
        rex     4
   bretagne     3
     cinema     3
   korrigan     3
       quai     3
      armor     2
   baladins     2
     bobine     2
      breiz     2
        cgr     2</span></pre>
<h3>Sur une carte</h3>
<a href="http://data-bzh.fr/wp-content/uploads/2017/09/map-cine-bretagne.png"><img class="aligncenter size-full wp-image-3697" src="http://data-bzh.fr/wp-content/uploads/2017/09/map-cine-bretagne.png" alt="" width="1200" height="600" /></a>