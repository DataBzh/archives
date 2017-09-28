---
ID: 2259
post_title: >
  Les entreprises en Bretagne
  administrative
author: Michel Caradec
post_excerpt: ""
layout: post
permalink: >
  http://data-bzh.fr/entreprises-bretagne-administrative/
published: true
post_date: 2017-01-29 18:00:16
---
<h2>Dans ce billet, nous allons nous intéresser aux entreprises en Bretagne administrative.
<!--more--></h2>
[Tweet " #Sirene #Opendata — Les entreprises en #Bretagne administrative"]
<h3>Données</h3>
La <a href="https://www.legifrance.gouv.fr/eli/loi/2016/10/7/ECFI1524250L/jo/texte">loi pour une République numérique</a> a entraîné une ouverture des données publiques. A cette occasion, les informations sur les entreprises et leurs établissements (aussi appelée <strong><a href="http://www.sirene.fr/">base Sirene</a></strong>) sont <a href="http://www.data.gouv.fr/fr/datasets/base-sirene-des-entreprises-et-de-leurs-etablissements-siren-siret/">disponibles en Open Data</a> depuis le 1er janvier 2017.
<h3>Analyse exploratoire</h3>
Le nombre d’établissements référencés en Bretagne administrative est de <strong>468 108</strong>, pour un total de <strong>424 573</strong> entreprises (une entreprise pouvant avoir plusieurs établissements).

Par rapport à la France, qui compte <strong>10 538 425</strong> établissements (pour <strong>9 443 008</strong> entreprises), les établissements bretons représentent <strong>4.44%</strong> de la totalité du territoire.

<img class="aligncenter size-full wp-image-2248" src="http://dev.data-bzh.fr/wp-content/uploads/2017/01/01-etab_dept-2.png" alt="Etablissements par département" width="1200" height="600" />

C’est en <strong>Ille et Vilaine</strong> que sont implantés le plus d’établissements, suivi du Finistère, du Morbihan et des Côtes d’Armor.

<img class="aligncenter size-full wp-image-2249" src="http://dev.data-bzh.fr/wp-content/uploads/2017/01/02-naf_histogram-2.png" alt="Etablissements par activité" width="1200" height="600" />

L’activité <strong>L</strong> (<strong>Activités immobilières</strong>) est sans conteste la plus représentée en nombre d’établissements. Viennent ensuite les activités <strong>Commerce; réparation d'automobiles et de motocycles</strong> et <strong>Agriculture, sylviculture et pêche</strong>.

Le tableau suivant liste tous les codes d’activité.
<table>
<thead>
<tr>
<th style="text-align: center;" align="left">Code</th>
<th style="text-align: center;" align="left">Libellé</th>
</tr>
</thead>
<tbody>
<tr>
<td align="left">A</td>
<td align="left">Agriculture, sylviculture et pêche</td>
</tr>
<tr>
<td align="left">B</td>
<td align="left">Industries extractives</td>
</tr>
<tr>
<td align="left">C</td>
<td align="left">Industrie manufacturière</td>
</tr>
<tr>
<td align="left">D</td>
<td align="left">Production et distribution d'électricité, de gaz, de vapeur et d'air conditionné</td>
</tr>
<tr>
<td align="left">E</td>
<td align="left">Production et distribution d'eau ; assainissement, gestion des déchets et dépollution</td>
</tr>
<tr>
<td align="left">F</td>
<td align="left">Construction</td>
</tr>
<tr>
<td align="left">G</td>
<td align="left">Commerce ; réparation d'automobiles et de motocycles</td>
</tr>
<tr>
<td align="left">H</td>
<td align="left">Transports et entreposage</td>
</tr>
<tr>
<td align="left">I</td>
<td align="left">Hébergement et restauration</td>
</tr>
<tr>
<td align="left">J</td>
<td align="left">Information et communication</td>
</tr>
<tr>
<td align="left">K</td>
<td align="left">Activités financières et d'assurance</td>
</tr>
<tr>
<td align="left">L</td>
<td align="left">Activités immobilières</td>
</tr>
<tr>
<td align="left">M</td>
<td align="left">Activités spécialisées, scientifiques et techniques</td>
</tr>
<tr>
<td align="left">N</td>
<td align="left">Activités de services administratifs et de soutien</td>
</tr>
<tr>
<td align="left">O</td>
<td align="left">Administration publique</td>
</tr>
<tr>
<td align="left">P</td>
<td align="left">Enseignement</td>
</tr>
<tr>
<td align="left">Q</td>
<td align="left">Santé humaine et action sociale</td>
</tr>
<tr>
<td align="left">R</td>
<td align="left">Arts, spectacles et activités récréatives</td>
</tr>
<tr>
<td align="left">S</td>
<td align="left">Autres activités de services</td>
</tr>
<tr>
<td align="left">T</td>
<td align="left">Activités des ménages en tant qu'employeurs ; activités indifférenciées des ménages en tant que producteurs de biens et services pour usage propre</td>
</tr>
<tr>
<td align="left">U</td>
<td align="left">Activités extra-territoriales</td>
</tr>
</tbody>
</table>
On retrouve la même activité en première position pour tous les départements. Les <strong>Côtes d’Armor</strong> se démarquent du reste de la région, avec en seconde position l’activité <strong>A</strong> (<strong>Agriculture, sylviculture et pêche</strong>).

<img class="aligncenter size-full wp-image-2250" src="http://dev.data-bzh.fr/wp-content/uploads/2017/01/04-etab_by_cat-2.png" alt="Etablissements par catégorie" width="1200" height="600" />

Les <strong>PMEs</strong> sont représentées avec une majorité écrasante (<strong>92.3%</strong> des établissements), et vient confirmer le fait qu’elles sont le <a href="http://www.cpme.fr/indices/voir/503/les-pme-principaux-employeurs-de-france">premier employeur de France</a>, tout comme en Bretagne, comme le montre le graphique ci-dessous, qui comptabilise l’effectif par catégorie.

<img class="aligncenter size-full wp-image-2251" src="http://dev.data-bzh.fr/wp-content/uploads/2017/01/05-effectif_by_cat-2.png" alt="Effectif par catégorie" width="1200" height="600" />

<span style="text-decoration: underline;">Notes d’implémentation</span>

Le calcul de l’effectif n’est qu’une estimation, sur la base de ce qui est déclaré par les établissements (la dernière actualisation n’étant pas toujours récente), et en moyennisant les tranches d’effectif communiquées par l’INSEE (par exemple, la tranche 100-199 comptera pour un effectif de 149 personnes).

Concernant les catégories des établissements, selon la <a href="http://www.sirene.fr/sirene/public/static/contenu-fichiers">définition de l’INSEE</a> :
<ul>
 	<li><em>Une Petite ou Moyenne Entreprise (PME) emploie moins de 250 salariés, avec un chiffre d’affaires annuel inférieur à 50 millions d’euros ou un total de bilan n’excédant pas 43 millions d’euros. Cette catégorie inclut les microentreprises.</em></li>
 	<li><em>Une Entreprise de Taille Intermédiaire (ETI) emploie entre 250 et 4999 salariés, avec un chiffre d’affaires n’excédant pas 1,5 milliards d’euros soit un total de bilan n’excédant pas 2 milliards d’euros.</em></li>
 	<li><em>Une Grande Entreprise (GE) emploie au moins 5000 salariés.</em></li>
</ul>
Cas particuliers :
<ul>
 	<li><em>Une entreprise qui a moins de 250 salariés, mais plus de 50 millions d’euros de chiffre d’affaires et plus de 43 millions d’euros de total de bilan est aussi considérée comme une ETI.</em></li>
 	<li><em>Une entreprise qui a moins de 5000 salariés mais plus de 1,5 milliards d’euros de chiffre d’affaires et plus de 2 milliards d’euros de total de bilan est aussi considérée comme une grande entreprise.</em></li>
</ul>
Dans le cas de la base Sirene, la variable <strong>catégorie</strong> n’est pas obligatoirement renseignée (ce qui est souvent le cas pour les PMEs). Une détection automatique a été effectuée avec de déterminer les valeurs manquantes, sur la base de l’effectif (les informations concernant le chiffre d’affaires n’étant pas présentes dans la base Sirene).

Poursuivons avec l'implantation par département des Grandes Entreprises.

<img class="aligncenter size-full wp-image-2260" src="http://dev.data-bzh.fr/wp-content/uploads/2017/01/06-ge_by_dept-1-2.png" alt="" width="1200" height="600" />

C’est l’<strong>Ille et Vilaine</strong> qui l’emporte, avec <strong>43.54%</strong> des établissements de catégorie <strong>GE</strong>.

Considérons les établissements non pas en fonction de leur catégorie, mais de leur effectif (même s’il existe un lien entre les deux, qui peut éventuellement être altéré par le chiffre d’affaires, comme nous l’avons précédemment évoqué).

<img class="aligncenter size-full wp-image-2253" src="http://dev.data-bzh.fr/wp-content/uploads/2017/01/07-effectif_hist-2.png" alt="Etablissements par tranche d'effectif" width="1200" height="600" />

Les établissements sans salariés (c’est à dire uniquement constitué de gérants) dominent largement (<strong>78.71%</strong>). Il s’agit essentiellement de <strong>PMEs</strong>, comme nous le confirme ce tableau comptabilisant le nombre d’établissements par catégorie et tranche d’effectif.

<img class="aligncenter size-full wp-image-2254" src="http://dev.data-bzh.fr/wp-content/uploads/2017/01/08-effectif_by_cat_heatmap-2.png" alt="Etablissements par tranche d'effectif et catégorie" width="1200" height="600" />

Afin de mieux comparer les autres établissements, excluons les établissements sans salariés de notre jeu de données.

<img class="aligncenter size-full wp-image-2255" src="http://dev.data-bzh.fr/wp-content/uploads/2017/01/09-effectif_no_zero_hist-2.png" alt="Etablissements par tranche d'effectif (au - 1 salarié)" width="1200" height="600" />

Il y a <strong>3</strong> établissements de <strong>plus de 5 000 salariés</strong>. Il s’agit de :
<ul>
 	<li><strong>Centre Hospitalier Régional et Universitaire de Brest</strong> (effectif déclaré en <strong>2015</strong> = <strong>7 900</strong>).</li>
 	<li><strong>Centre Hospitalier Universitaire de Pontchaillou</strong> (effectif déclaré en <strong>2015</strong> = <strong>9 300</strong>).</li>
 	<li><strong>Automobiles Citroën</strong> (effectif déclaré en <strong>1998</strong> = <strong>9 000</strong>).</li>
</ul>
<span style="text-decoration: underline;">Remarques</span>
<ul>
 	<li>L’effectif est donné à la centaine prêt.</li>
 	<li>On peut s'interroger sur la pertinence de l'effectif de Citroën, dont la dernière mise à jour remonte à <strong>1998</strong>.</li>
</ul>
Où se trouvent les établissements de 200 salariés et plus ?

<img class="aligncenter size-full wp-image-2256" src="http://dev.data-bzh.fr/wp-content/uploads/2017/01/10-effectif200_by_dept-2.png" alt="Etablissements de 200 salariés et plus par département" width="1200" height="600" />

Les établissements de <strong>200 salariés et plus</strong> sont au nombre de <strong>565</strong> (<strong>0.12%</strong> de la totalité).

Les entreprise avec le plus d’établissements sont :
<table class="table table-condensed">
<thead>
<tr class="header">
<th>SIREN</th>
<th>Dénomination</th>
<th>Etablissements</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>356 000 000</td>
<td>La Poste</td>
<td>596</td>
</tr>
<tr class="even">
<td>775 577 018</td>
<td>Crédit Mutuel Arkea</td>
<td>451</td>
</tr>
<tr class="odd">
<td>392 640 090</td>
<td>Caisse d’épargne et de prévoyance Bretagne - Pays de Loire</td>
<td>203</td>
</tr>
<tr class="even">
<td>775 576 986</td>
<td>Triskalia</td>
<td>194</td>
</tr>
<tr class="odd">
<td>445 330 236</td>
<td>Distrivert</td>
<td>188</td>
</tr>
<tr class="even">
<td>814 844 346</td>
<td>Newco</td>
<td>154</td>
</tr>
<tr class="odd">
<td>552 081 317</td>
<td>Electricité de France</td>
<td>149</td>
</tr>
<tr class="even">
<td>213 502 388</td>
<td>Commune de Rennes</td>
<td>145</td>
</tr>
<tr class="odd">
<td>778 134 601</td>
<td>Caisse régionales de crédit agricole mutuel du Finistère</td>
<td>141</td>
</tr>
<tr class="even">
<td>334 159 472</td>
<td>Ansamble</td>
<td>130</td>
</tr>
</tbody>
</table>
Terminons cette exploration par une cartographie.

<img class="aligncenter size-full wp-image-2257" src="http://dev.data-bzh.fr/wp-content/uploads/2017/01/11-etab_map-2.png" alt="Emplacement des établissements" width="1200" height="600" />
<h3>Conclusion</h3>
Cette étude n’est qu’un exemple de ce qu’il est possible de réaliser à partir de la <strong><a href="http://www.sirene.fr/">base Sirene</a></strong>. De nombreuses possibilités sont offertes de par la richesse de celle-ci (une <strong>centaine</strong> de variables descriptives sont disponibles). On pourra par exemple aller plus loin en enrichissant ces données avec des informations de géolocalisation (en s’appuyant sur la <a href="http://adresse.data.gouv.fr/">base adresse nationale</a>) ou financières (données <a href="https://datainfogreffe.fr/">InfoGreffe</a>).

<span style="text-decoration: underline;">Notes d’implémentation</span>
<ul>
 	<li>La taille du fichier de stock <strong>Sirene</strong> (contenant les informations initiales) de <strong>8.5 Go</strong> rend difficile son exploitation avec les outils d’analyse de données traditionnels, comme un tableur ou <strong><a href="https://cran.r-project.org/">R</a></strong>, qui requièrent un chargement des données en mémoire. Afin de réduire cette taille, seules les données clés ont été conservées (par exemple, l’intitulé du code activité a été supprimé, car pouvant être retrouvé via une table de correspondance à partir du code), permettant ainsi de réduire la taille à <strong>2 Go</strong>. L’utilitaire <strong>Python</strong> développé pour cette opération est disponible <a href="https://github.com/michelcaradec/projector">ici</a>.</li>
 	<li>Les besoins de géolocalisation étant élémentaires (sans nécessité d’une grande précision), un utilitaire <strong>R</strong> a été développé afin d’obtenir des coordonnées longitude/latitude à partir d’un code postal. Le code est disponible <a href="https://github.com/michelcaradec/Rgeo">ici</a>.</li>
 	<li>Le code <strong>R</strong> utilisé pour la rédaction de cet article est disponible sur notre dépôt de sources <a href="https://github.com/DataBzh/territoire/tree/master/sirene">Github</a>.</li>
</ul>