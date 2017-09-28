---
ID: 2329
post_title: 'Noms des entreprises en Bretagne administrative &#8211; Partie 1'
author: Michel Caradec
post_excerpt: ""
layout: post
permalink: >
  http://data-bzh.fr/noms-entreprises-bretagne-administrative-partie-1/
published: true
post_date: 2017-02-13 18:00:23
---
<h2>Dans un <a href="http://data-bzh.fr/entreprises-bretagne-administrative/">précédent billet</a>, nous nous étions intéressé aux entreprises en Bretagne administrative, sous l’angle de l’activité, de la catégorie ou encore de l’effectif.</h2>
<h2>Nous allons nous cette fois-ci nous focaliser sur le nom des entreprises.
<!--more--></h2>
[Tweet "#Noms des #entreprises en #Bretagne administrative - Partie 1"]
<h2>Données</h2>
Les informations sur les entreprises et leurs établissements proviennent de la <a href="http://www.sirene.fr/">base Sirene</a>, <a href="http://www.data.gouv.fr/fr/datasets/base-sirene-des-entreprises-et-de-leurs-etablissements-siren-siret/">disponible en Open Data</a> sur le site <a href="http://www.data.gouv.fr/">data.gouv.fr</a>.

Les entreprises répertoriées dans ce jeu de données peuvent-être classées en 2 catégories :
<ol>
 	<li>Les entreprises.</li>
 	<li>Les entrepreneurs individuels.</li>
</ol>
Nous ne traiterons ici que la première catégorie, celle des <strong>entreprises</strong>. La dénomination d’une entreprise individuelle pouvant essentiellement être constituée par le nom de la personne morale la possédant, cette étude porterait alors sur des patronymes plutôt que sur des noms communs.

Précisons que la base <strong>Sirene</strong> recense le <strong>nom d’exploitation</strong> de la société ainsi que le <strong>nom de l’enseigne</strong>, qui peuvent parfois être différents. C’est le <strong>nom d’exploitation</strong> que nous utiliserons ici.
<h2>Analyse exploratoire</h2>
Pour <a href="http://data-bzh.fr/entreprises-bretagne-administrative/">mémoire</a>, le nombre d’établissements référencés en Bretagne administrative est de <strong>468 108</strong>.

<img class="aligncenter size-full wp-image-2331" src="http://dev.data-bzh.fr/wp-content/uploads/2017/02/01-civilite-2.png" alt="Etablissements par type" width="1200" height="600" />

Les entreprises non-individuelles, que nous étudierons ici, représentent <strong>61.4%</strong> de la totalité.

<img class="aligncenter size-full wp-image-2332" src="http://dev.data-bzh.fr/wp-content/uploads/2017/02/02-length_histogram-2.png" alt="Nombre de caractères par nom d'établissement" width="1200" height="600" />

Le nombre moyen de caractères du nom d’un établissement est de <strong>21</strong> (nombre médian de <strong>18</strong>, représenté par la ligne en pointillés).

Le nombre d’établissements diminue régulièrement à partir de <strong>14</strong> caractères, avec une distribution à <strong><a href="https://en.wikipedia.org/wiki/Skewness">coefficient de dissymétrie</a> positif</strong> (positive skew distribution). Une exception apparaît pour les noms composés de <strong>38</strong> caractères (<strong>6 128</strong> occurrences). Aucun élément présent dans le jeu de données ne permet d’expliquer ce phénomène, probablement dû au simple fait du hasard.

Mise à jour du 01/04/2017 :

<em>Le pic de dénominations de 38 caractères a en fait une explication, qui nous a été donnée par un interlocuteur de l'INSEE (que nous remercions). Le champ de dénomination de la base Sirene était limité à 38 caractères jusque dans les années 1990 (il est ensuite passé à 120 caractères). Les gestionnaires faisaient donc en sorte de consigner cette dénomination sur 38 caractères, en abrégeant certains mots. On observe ainsi un arrêt de la décroissance du nombre de dénominations entre 35 et 37 caractères.</em>

Passons au nombre de mots par nom d’établissement.

<img class="aligncenter size-full wp-image-2333" src="http://dev.data-bzh.fr/wp-content/uploads/2017/02/03-wordcount_hist-2.png" alt="Nombre de mots par nom d'établissement" width="1200" height="600" />

Visualisons la même information sous la forme d’une <strong><a href="https://fr.wikipedia.org/wiki/Bo%C3%AEte_%C3%A0_moustaches">boite à moustaches</a></strong>.

<img class="aligncenter size-full wp-image-2334" src="http://dev.data-bzh.fr/wp-content/uploads/2017/02/04-wordcount_boxplot-2.png" alt="Nombre de mots par nom d'établissement" width="1200" height="600" />

<strong>50%</strong> des noms sont composés de <strong>2 à 5</strong> mots.

Regardons quelle est la distribution du nombre de mots en fonction de l’activité.

<img class="aligncenter size-full wp-image-2335" src="http://dev.data-bzh.fr/wp-content/uploads/2017/02/05-wordcount_naf-2.png" alt="Nombre de mots par activité" width="1200" height="600" />

Les établissements d’activité <strong>E</strong>, <strong>O</strong>, <strong>P</strong>, <strong>Q</strong> et <strong>U</strong> (respectivement <strong>Production et distribution d’eau ; assainissement, gestion des déchets et dépollution / Administration publique / Enseignement / Santé humaine et action sociale / Activités extra-territoriales</strong>) ont des noms avec un plus grand nombre de mots que pour les autres activités. Ceci s’explique notamment par le fait que le nom, en plus de la désignation de l’activité, peut contenir le lieu d’action (exemples : “Préfecture du département du Finistère”, “Chambre commerce et industrie de Morlaix”, “Dir interdep routes ouest cei de Brest”, etc.).

Le tableau suivant liste tous les codes d’activité.
<table>
<thead>
<tr>
<th style="text-align: left;" align="left">Code</th>
<th style="text-align: left;" align="left">Libellé</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align: left;" align="left">A</td>
<td style="text-align: left;" align="left">Agriculture, sylviculture et pêche</td>
</tr>
<tr>
<td style="text-align: left;" align="left">B</td>
<td style="text-align: left;" align="left">Industries extractives</td>
</tr>
<tr>
<td style="text-align: left;" align="left">C</td>
<td style="text-align: left;" align="left">Industrie manufacturière</td>
</tr>
<tr>
<td style="text-align: left;" align="left">D</td>
<td style="text-align: left;" align="left">Production et distribution d'électricité, de gaz, de vapeur et d'air conditionné</td>
</tr>
<tr>
<td style="text-align: left;" align="left">E</td>
<td style="text-align: left;" align="left">Production et distribution d'eau ; assainissement, gestion des déchets et dépollution</td>
</tr>
<tr>
<td style="text-align: left;" align="left">F</td>
<td style="text-align: left;" align="left">Construction</td>
</tr>
<tr>
<td style="text-align: left;" align="left">G</td>
<td style="text-align: left;" align="left">Commerce ; réparation d'automobiles et de motocycles</td>
</tr>
<tr>
<td style="text-align: left;" align="left">H</td>
<td style="text-align: left;" align="left">Transports et entreposage</td>
</tr>
<tr>
<td style="text-align: left;" align="left">I</td>
<td style="text-align: left;" align="left">Hébergement et restauration</td>
</tr>
<tr>
<td style="text-align: left;" align="left">J</td>
<td style="text-align: left;" align="left">Information et communication</td>
</tr>
<tr>
<td style="text-align: left;" align="left">K</td>
<td style="text-align: left;" align="left">Activités financières et d'assurance</td>
</tr>
<tr>
<td style="text-align: left;" align="left">L</td>
<td style="text-align: left;" align="left">Activités immobilières</td>
</tr>
<tr>
<td style="text-align: left;" align="left">M</td>
<td style="text-align: left;" align="left">Activités spécialisées, scientifiques et techniques</td>
</tr>
<tr>
<td style="text-align: left;" align="left">N</td>
<td style="text-align: left;" align="left">Activités de services administratifs et de soutien</td>
</tr>
<tr>
<td style="text-align: left;" align="left">O</td>
<td style="text-align: left;" align="left">Administration publique</td>
</tr>
<tr>
<td style="text-align: left;" align="left">P</td>
<td style="text-align: left;" align="left">Enseignement</td>
</tr>
<tr>
<td style="text-align: left;" align="left">Q</td>
<td style="text-align: left;" align="left">Santé humaine et action sociale</td>
</tr>
<tr>
<td style="text-align: left;" align="left">R</td>
<td style="text-align: left;" align="left">Arts, spectacles et activités récréatives</td>
</tr>
<tr>
<td style="text-align: left;" align="left">S</td>
<td style="text-align: left;" align="left">Autres activités de services</td>
</tr>
<tr>
<td style="text-align: left;" align="left">T</td>
<td style="text-align: left;" align="left">Activités des ménages en tant qu'employeurs ; activités indifférenciées des ménages en tant que producteurs de biens et services pour usage propre</td>
</tr>
<tr>
<td style="text-align: left;" align="left">U</td>
<td align="left">Activités extra-territoriales</td>
</tr>
</tbody>
</table>
Travaillons maintenant sur les mots en eux-même.

<img class="aligncenter size-full wp-image-2336" src="http://dev.data-bzh.fr/wp-content/uploads/2017/02/07-wordcount-2.png" alt="20 mots les plus utilisés" width="1200" height="600" />

Le nombre d’occurrences du mot <strong>sci</strong> représente <strong>5.43%</strong> de la totalité, écrasant le reste de la distribution, avec <strong>1 081 976</strong> occurrences, qui descend à <strong>198 313</strong> pour le second mot <strong>sarl</strong>.

La présence de ce mot vient confirmer le constat effectué dans notre <a href="http://data-bzh.fr/entreprises-bretagne-administrative/">précédent article</a>, dans lequel nous avions mis en évidence la forte représentation de l’activité <strong>L</strong> (<strong>Activités immobilières</strong>) en termes de nombre d’établissements.

Terminons par un <strong><a href="https://fr.wikipedia.org/wiki/Nuage_de_mots-cl%C3%A9s">nuage de mots</a></strong>, dans lequel nous avons volontairement exclu le mot <strong>sci</strong>, dont la présence aurait pour effet d’écraser les autres mots (la taille d’affichage étant proportionnelle au nombre d’occurrences).

<img class="aligncenter size-full wp-image-2337" src="http://dev.data-bzh.fr/wp-content/uploads/2017/02/08-wordcloud-2.png" alt="Nuage de mots" width="1200" height="600" />
<h2>Conclusion</h2>
Ainsi s’achève la première partie de notre série sur les noms des entreprises en Bretagne administrative.

La suite dans un prochain article.