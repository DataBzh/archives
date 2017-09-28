---
ID: 3631
post_title: La Bretagne vue par Atout France
author: Colin FAY
post_excerpt: ""
layout: post
permalink: >
  http://data-bzh.fr/la-bretagne-vue-par-atout-france/
published: true
post_date: 2017-08-08 18:00:33
---
<h2>Exploration des 5 jeux de données mis en ligne par Atout France sur data.gouv, pour un aperçu du tourisme en Bretagne administrative.<!--more--></h2>
<h3>À propos d'Atout France</h3>
<em>L'Agence de développement touristique de la France, est chargée par la loi du 22 juillet 2009 sur le développement et la modernisation des services touristiques, de contribuer au développement de l'industrie touristique, premier secteur économique français et de l'ensemble de ses acteurs (<a href="https://www.data.gouv.fr/fr/organizations/atout-france-agence-de-developpement-touristique-de-la-france/">source</a>).</em>

[Tweet "#DataViz #Tourisme — La #Bretagne vue par @atout_france"]
<h3>Les jeux de données</h3>
Voici les cinq jeux de données que nous utilisons ici :
<ul>
 	<li><a href="https://www.data.gouv.fr/fr/datasets/parcs-residentiels-de-loisirs-classes-en-france/">Parcs résidentiels de loisirs classés en France</a></li>
 	<li><a href="https://www.data.gouv.fr/fr/datasets/villages-de-vacances-classes-en-france/">Villages de vacances classés en France</a></li>
 	<li><a href="https://www.data.gouv.fr/fr/datasets/residences-de-tourisme-classees-en-france/">Résidences de tourisme classées en France</a></li>
 	<li><a href="https://www.data.gouv.fr/fr/datasets/hotels-classes-en-france/">Hôtels classés en France</a></li>
 	<li><a href="https://www.data.gouv.fr/fr/datasets/campings-classes-en-france/">Campings classés en France</a></li>
</ul>
Une fois ces jeux de données triés et concaténés, nous comptons 1401 établissements classés, répartis dans ces cinq catégories.
<h3>Par département et par typologie</h3>
Voici comment se répartissent ces établissements, par type et par département :
<pre id="rstudio_console_output" class="GNKRCKGCFSB" tabindex="0"><span class="GNKRCKGCFSB">                                         22  29  35  56
  Campings classés                      109 212  60 206
  Hôtels classés                        134 189 204 192
  Parcs résidentiels de loisirs classés   1   1   0   3
  Résidences de tourisme classées         7  27  18  10
  Villages de vacances classés            7  12   1   8</span></pre>
Soit, en dataviz : <a href="http://data-bzh.fr/wp-content/uploads/2017/08/atout-france-type-departement.png"><img class="aligncenter size-full wp-image-3634" src="http://data-bzh.fr/wp-content/uploads/2017/08/atout-france-type-departement.png" alt="" width="1200" height="600" /></a>

Ce sont <strong>le Finistère et le Morbihan qui comptent le plus d'établissements touristiques classés et recensés par Atout France</strong> — les deux grands types étant Campings et Hôtels. Très peu de Parc de loisirs sont recensés dans la région bretonne.
<h3>Classement par étoiles</h3>
Intéressons nous maintenant au classement par nombre d'étoiles de ces établissements.

<a href="http://data-bzh.fr/wp-content/uploads/2017/08/atout-france-classement.png"><img class="aligncenter size-full wp-image-3636" src="http://data-bzh.fr/wp-content/uploads/2017/08/atout-france-classement.png" alt="" width="1200" height="600" /></a>

Majoritairement, les établissements affichent 2 ou 3 étoiles. On remarque que la part des autres classements est très faible, en comparaison.

Découpons ensuite en fonction du département :
<pre id="rstudio_console_output" class="GNKRCKGCFSB" tabindex="0"><span class="GNKRCKGCFSB">                  22  29  35  56
  1 étoile        12  28  16  15
  2 étoiles       97 167 101 167
  3 étoiles      121 166 125 187
  4 étoiles       23  70  32  44
  5 étoiles        5   8   9   6
  Aire naturelle   0   2   0   0</span></pre>
Et si nous passons ces classements en dataviz :

<a href="http://data-bzh.fr/wp-content/uploads/2017/08/atout-france-classement-dep.png"><img class="aligncenter size-full wp-image-3637" src="http://data-bzh.fr/wp-content/uploads/2017/08/atout-france-classement-dep.png" alt="" width="1200" height="600" /></a>

Si l'on s'en tient aux proportions, c'est en Ille-et-Vilaine qu'il y a le plus d'établissements 5 étoiles, et le Finistère qui compte le plus de 4 étoiles. La part des établissements 1 étoiles est relativement comparable d'un département à l'autre.
<h3>Par communes</h3>
Quelles sont les 15 communes les plus représentées ?
<pre id="rstudio_console_output" class="GNKRCKGCFSB" tabindex="0"><span class="GNKRCKGCFSB">         COMMUNE Volume
1     SAINT-MALO     67
2         RENNES     37
3          BREST     30
4         CARNAC     28
5      FOUESNANT     26
6         VANNES     24
7       QUIBERON     23
8        CANCALE     21
9  PERROS-GUIREC     21
10    DOUARNENEZ     19
11         AMBON     17
12        DINARD     17
13       SARZEAU     17
14       BÉNODET     16
15        CROZON     16</span></pre>
C'est <strong>Saint-Malo qui remporte haut la main ce classement des villes les plus représentées dans notre jeu de données</strong>, avec 67 unités — soit presque le double de la ville de rang 2, Rennes, avec 37 unités.

Maintenant, quelles sont les communes avec le plus d'établissements par habitant ?
<pre id="rstudio_console_output" class="GNKRCKGCFSB" tabindex="0"><span class="GNKRCKGCFSB">                 COMMUNE DEPARTEMENT ETABLISSEMENTS POPULATION    ETAB/POP
1       plessix-balisson          22              1         89 0.011235955
2                  ambon          56             17       1794 0.009476031
3                 damgan          56             15       1656 0.009057971
4              trégarvan          29              1        143 0.006993007
5                 carnac          56             28       4183 0.006693760
6  saint-pierre-quiberon          56             12       2116 0.005671078
7               île-tudy          29              4        742 0.005390836
8                 bangor          56              5        957 0.005224660
9          saint-launeuc          22              1        197 0.005076142
10               bénodet          29             16       3442 0.004648460
11              quiberon          56             23       4987 0.004611991
12  saint-cast-le-guildo          22             15       3449 0.004349087
13               roscoff          29             14       3434 0.004076878
14           île-d'houat          56              1        246 0.004065041
15               cancale          35             21       5208 0.004032258</span></pre>
Soit, en dataviz :

<a href="http://data-bzh.fr/wp-content/uploads/2017/08/atout-france-etab-pop.png"><img class="aligncenter size-full wp-image-3647" src="http://data-bzh.fr/wp-content/uploads/2017/08/atout-france-etab-pop.png" alt="" width="1200" height="600" /></a>
<h3>Carte de Bretagne</h3>
Et si nous plaçons ces établissements sur une carte :

<a href="http://data-bzh.fr/wp-content/uploads/2017/08/atout-france-carte-bretagne-etab.png"><img class="aligncenter size-full wp-image-3650" src="http://data-bzh.fr/wp-content/uploads/2017/08/atout-france-carte-bretagne-etab.png" alt="" width="1200" height="600" /></a>

Nous voyons, presque sans surprise, <strong>que la plupart des villes comptant beaucoup d'établissements se situent sur la côte</strong>. Et pour cause, le littoral reste un espace plus touristique que l'intérieur des terres.
<h3>Capacité d'accueil</h3>
Voici la répartition des capacités d'accueil des établissements.

<em>Note : 592 lignes n'ont pas été prises en compte car non renseignées.</em>

<a href="http://data-bzh.fr/wp-content/uploads/2017/08/atout-france-capacite-accueil.png"><img class="aligncenter size-full wp-image-3640" src="http://data-bzh.fr/wp-content/uploads/2017/08/atout-france-capacite-accueil.png" alt="" width="1200" height="600" /></a>

On voit que l'immense majorité des établissements ont une faible capacité d'accueil (moins de 100 places). En tête de liste, la Résidence Ker Goh Lenn, qui affiche 724 places, et l'Hôtel Restaurant Au Chêne Vert (615 places).

Et si l'on découpe par département et par classement :

<a href="http://data-bzh.fr/wp-content/uploads/2017/08/atout-france-capacite-accueil-dep-classement.png"><img class="aligncenter size-full wp-image-3641" src="http://data-bzh.fr/wp-content/uploads/2017/08/atout-france-capacite-accueil-dep-classement.png" alt="" width="1200" height="600" /></a>
<h3>Les noms commerciaux</h3>
Quels sont les termes les plus courants que l'on peut trouver dans les noms commerciaux de ces établissements ?

<em>Note : nous avons retiré les termes "hôtels", "restaurant", "résidence", "camping", "parc" et "loisirs".</em>

<a href="http://data-bzh.fr/wp-content/uploads/2017/08/atout-france-text-mining-nom-etablissements.png"><img class="aligncenter size-full wp-image-3644" src="http://data-bzh.fr/wp-content/uploads/2017/08/atout-france-text-mining-nom-etablissements.png" alt="" width="1200" height="600" /></a>

Ici, peu de surprise quant aux termes les plus utilisés : "municipal", très souvent accompagné par camping, "saint", qui reste très présents de manière globale lorsque l'on s'intéresse aux noms en Bretagne (voir <a href="http://data-bzh.fr/geofla-communes-2015-en-bretagne/" target="_blank" rel="noopener noreferrer">ici</a> et <a href="http://data-bzh.fr/bars-pubs-bretagne/" target="_blank" rel="noopener noreferrer">ici</a>).

Le code sur notre <a href="https://github.com/DataBzh/territoire" target="_blank" rel="noopener noreferrer">Github</a> !