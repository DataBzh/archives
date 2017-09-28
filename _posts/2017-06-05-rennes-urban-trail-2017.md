---
ID: 3513
post_title: Rennes Urban Trail 2017
author: Michel Caradec
post_excerpt: ""
layout: post
permalink: >
  http://data-bzh.fr/rennes-urban-trail-2017/
published: true
post_date: 2017-06-05 18:00:20
---
<h2>Le dimanche <strong>2 avril 2017</strong> s’est déroulé le premier <a href="http://www.rennesurbantrail.bzh">Urban Trail de Rennes</a>.
<!--more-->
[Tweet "#Rennes — Retour en #DataViz sur le premier @UrbanRennes !"]</h2>
L’évènement regroupait les adeptes de la course à pied autour de <strong>3 épreuves</strong> de <strong><a href="http://www.rennesurbantrail.bzh/7-km.php">7 km</a></strong>, <strong><a href="http://www.rennesurbantrail.bzh/14-km.php">14 km</a></strong> et <strong><a href="http://www.rennesurbantrail.bzh/24-km.php">24 km</a></strong>, sur des circuits alternants zones “roulantes” et passages plus techniques (montées/descentes d’escaliers, parcours en zone nature, etc.).

Dans ce billet, nous allons nous intéresser aux résultats des différentes épreuves.
<div id="donnees" class="section level2">
<h2>Données</h2>
Le résultat des courses est disponible sur le site <strong><a href="https://www.klikego.com/resultats/rennes-urban-trail-2017/1477428861475-1">Klikego</a></strong>.

Ceux-ci n’étant pas téléchargeables dans un format exploitable automatiquement, les données ont été récupérées à l’aide d’un outil prévu à cet effet : <strong><a href="https://github.com/michelcaradec/KlikegoScraper">KlikegoScraper</a></strong>.

</div>
<div id="analyse-exploratoire" class="section level2">
<h2>Analyse exploratoire</h2>
<strong>3 165</strong> participants (<strong>2 013</strong> hommes et <strong>1 152</strong> femmes) ont franchi la ligne d’arrivée (les “finishers”).

Regardons le détail par <strong>épreuve</strong>.

<img class="aligncenter size-full wp-image-3514" src="http://data-bzh.fr/wp-content/uploads/2017/06/01-race-count.png" alt="Urban Trail Rennes 2017 - Nombre de finishers par épreuve" width="1200" height="600" />

C’est le <strong>14 km</strong> qui a réuni le plus de participants. Le <strong>24 km</strong> n’est pas en reste, preuve que la course à pied est un sport populaire (le succès des éditions de <a href="http://www.toutrennescourt.fr">Tout Rennes court</a> ne contrediront pas ce point).

Poursuivons notre analyse avec la répartition par <strong>sexe</strong>.

<img class="aligncenter size-full wp-image-3515" src="http://data-bzh.fr/wp-content/uploads/2017/06/02-race-sex-count.png" alt="Urban Trail Rennes 2017 - Nombre de finishers par sexe" width="1200" height="600" />

Les <strong>femmes</strong> sont plus représentées sur le <strong>7 km</strong>, mais leur proportion diminue avec l’augmentation de la distance. La tendance est inverse chez les <strong>hommes</strong>.

Regardons maintenant la répartition par <strong>catégorie</strong>.

<img class="aligncenter size-full wp-image-3516" src="http://data-bzh.fr/wp-content/uploads/2017/06/03-race-cat-count.png" alt="Urban Trail Rennes 2017 - Nombre de finishers par catégorie" width="1200" height="600" />

Chaque catégorie représente une tranche d’âge, avec un découpage détaillé sur le tableau suivant.
<table class="table table-condensed">
<thead>
<tr class="header">
<th>Catégorie</th>
<th>Sigle</th>
<th>Age</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="text-align: left;">Cadet</td>
<td style="text-align: left;">CA</td>
<td style="text-align: left;">de 16 à 17 ans</td>
</tr>
<tr class="even">
<td style="text-align: left;">Junior</td>
<td style="text-align: left;">JU</td>
<td style="text-align: left;">de 18 à 19 ans</td>
</tr>
<tr class="odd">
<td style="text-align: left;">Espoir</td>
<td style="text-align: left;">ES</td>
<td style="text-align: left;">de 20 à 22 ans</td>
</tr>
<tr class="even">
<td style="text-align: left;">Senior</td>
<td style="text-align: left;">SE</td>
<td style="text-align: left;">de 23 à 39 ans</td>
</tr>
<tr class="odd">
<td style="text-align: left;">Vétéran 1</td>
<td style="text-align: left;">V1</td>
<td style="text-align: left;">de 40 à 49 ans (35 ans au niveau international)</td>
</tr>
<tr class="even">
<td style="text-align: left;">Vétéran 2</td>
<td style="text-align: left;">V2</td>
<td style="text-align: left;">de 50 à 59 ans</td>
</tr>
<tr class="odd">
<td style="text-align: left;">Vétéran 3</td>
<td style="text-align: left;">V3</td>
<td style="text-align: left;">à partir de 60 ans</td>
</tr>
<tr class="even">
<td style="text-align: left;">Vétéran 4</td>
<td style="text-align: left;">V4</td>
<td style="text-align: left;">à partir de 70 ans (messieurs uniquement)</td>
</tr>
</tbody>
</table>
<em>Source <a href="https://fr.wikipedia.org/wiki/Catégorie_(sports)#Cat.C3.A9gories_en_athl.C3.A9tisme">Wikipedia</a></em>.

Les <strong>Seniors</strong> et <strong>Vétérans 1</strong> (aussi appelés Master 1) sont ceux qui ont le plus répondus présent.

Intéressons nous maintenant à l’<strong>âge</strong>.

Les concurrents les plus jeunes ont <strong>16 ans</strong> (au nombre de <strong>4</strong>), les plus anciens <strong>76 ans</strong> (au nombre de <strong>2</strong>).

Observons la distribution de l’âge pour les 3 épreuves.

<img class="aligncenter size-full wp-image-3517" src="http://data-bzh.fr/wp-content/uploads/2017/06/04-race-age-count.png" alt="Urban Trail Rennes 2017 - Nombre de finishers par âge" width="1200" height="600" />

Dans tous les cas, la distribution suit approximativement une <strong><a href="https://fr.wikipedia.org/wiki/Loi_normale">loi normale</a></strong>. Autrement dit, le nombre de concurrents est le plus important aux alentours de la moyenne d’âge, et diminue en allant vers les extrémités.

Voici quelques éléments statistiques complémentaires.
<table class="table table-condensed" cellspacing="0">
<thead>
<tr>
<th align="left">
<div class="pagedtable-header-name" style="text-align: left;">Course</div></th>
<th align="left">
<div class="pagedtable-header-name" style="text-align: left;">Temps Min.</div></th>
<th align="left">
<div class="pagedtable-header-name" style="text-align: left;">Temps Max.</div></th>
<th align="left">
<div class="pagedtable-header-name" style="text-align: left;">Temps Moyen</div></th>
<th align="left">
<div class="pagedtable-header-name" style="text-align: left;">Temps Median</div></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="text-align: left;" align="left">7km</td>
<td style="text-align: left;" align="left">0h26</td>
<td style="text-align: left;" align="left">1h06</td>
<td style="text-align: left;" align="left">0h47</td>
<td style="text-align: left;" align="left">0h47</td>
</tr>
<tr class="even">
<td style="text-align: left;" align="left">14km</td>
<td style="text-align: left;" align="left">0h53</td>
<td style="text-align: left;" align="left">2h05</td>
<td style="text-align: left;" align="left">1h28</td>
<td style="text-align: left;" align="left">1h28</td>
</tr>
<tr class="odd">
<td style="text-align: left;" align="left">24km</td>
<td style="text-align: left;" align="left">1h32</td>
<td style="text-align: left;" align="left">3h26</td>
<td style="text-align: left;" align="left">2h22</td>
<td style="text-align: left;" align="left">2h24</td>
</tr>
</tbody>
</table>
Regardons maintenant à l’aide d’<a href="https://fr.wikipedia.org/wiki/Histogramme">histogrammes</a> la distribution du temps nécessaire à l’accomplissement de chaque épreuve.

<img class="aligncenter size-full wp-image-3518" src="http://data-bzh.fr/wp-content/uploads/2017/06/06-race-hist.png" alt="Urban Trail Rennes 2017 - Distribution du temps par épreuve" width="1200" height="600" />

Visualisation la même information sous forme de <a href="https://fr.wikipedia.org/wiki/Boîte_à_moustaches">boîtes à moustache</a>.

<img class="aligncenter size-full wp-image-3519" src="http://data-bzh.fr/wp-content/uploads/2017/06/07-race-boxplot.png" alt="Urban Trail Rennes 2017 - Distribution du temps par épreuve" width="1200" height="600" />

Nous avons étudié séparément l’<strong>âge</strong> et le <strong>temps</strong>, mais existe-t-il un lien entre ces 2 éléments ? Nous pourrions être tentés de penser que les performances sont plus grandes pour les concurrents plus jeunes, et diminuent avec l’âge, mais qu’en est-il vraiment ?

Jusqu’à maintenant, nous avons utilisé la <strong>vitesse moyenne</strong>, qui est le nombre de kilomètres que l’on peut parcourir en une heure.

Nous allons ici nous référer à l’<strong>allure moyenne</strong>, qui est le nombre de minutes que l’on met pour parcourir un kilomètre (par exemple, une allure de 5 minutes signifie que l’on court à une vitesse de 12 km/h : en effet, il y a 12 segments de 5 minutes dans une heure). Ainsi, plus le nombre de minutes est bas, plus l’on court vite. Cette mesure est généralement privilégiée chez les coureurs, car plus simple à appréhender.

<em>Le calcul de l’allure moyenne a été effectué en divisant le temps de course par la distance</em>.

<img class="aligncenter size-full wp-image-3520" src="http://data-bzh.fr/wp-content/uploads/2017/06/08-age-pace.m.png" alt="Urban Trail Rennes 2017 - Allure moyenne en fonction de l'âge (hommes)" width="1200" height="600" />

</div>
<ul>
 	<li>La <strong>ligne bleue</strong> indique la tendance générale de l’allure par rapport à l’âge, et est calculée avec un modèle de <strong><a href="https://fr.wikipedia.org/wiki/Régression_linéaire">régression linéaire</a></strong>.</li>
 	<li>La <strong>zone grise</strong> indique l’intervalle de confiance.</li>
 	<li>Plus les <strong>points rouges</strong> sont sombres, plus la densité des coureurs pour un âge et une allure donnée est grande.</li>
</ul>
Chez les <strong>hommes</strong>, on observe une <strong>diminution de la vitesse avec l’âge</strong> (la ligne bleu est ascendante). Ce constat est le plus notable pour le <strong>7 km</strong>, probablement du fait des qualités d’explosivité qui sont particulièrement mises à contribution sur les courtes distances. La tendance <strong>diminue avec l’augmentation de la distance</strong> (qui sollicite plus des qualités d’endurance).

<img class="aligncenter size-full wp-image-3521" src="http://data-bzh.fr/wp-content/uploads/2017/06/09-age-pace.f.png" alt="Urban Trail Rennes 2017 - Allure moyenne en fonction de l'âge (femmes)" width="1200" height="600" />
<div id="analyse-exploratoire" class="section level2">

Chez les <strong>femmes</strong>, l’allure est <strong>relativement stable quel que soit l’âge</strong>, et ce pour <strong>toutes les courses</strong>.

<em>Notre analyse ne portant que sur 3 courses, les observations ne peuvent pas être généralisées</em>.

</div>
<div id="conclusion" class="section level2">
<h2>Conclusion</h2>
Ces différentes analyses sont autant d’occasions pour le coureur de se situer par rapport aux autres concurrents, et pourquoi pas de se fixer de nouveaux objectifs.

La prochaine édition de l’<strong>Urban Trail de Rennes</strong> aura lieu le <strong>22 avril 2018</strong>.

Le code <strong>R</strong> utilisé pour la rédaction de cet article est disponible sur notre dépôt de sources <a href="https://github.com/DataBzh/evenement/tree/master/RennesUrbanTrail2017">Github</a>.

</div>