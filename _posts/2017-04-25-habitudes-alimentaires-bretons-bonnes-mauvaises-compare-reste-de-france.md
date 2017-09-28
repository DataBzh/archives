---
ID: 3345
post_title: 'Les habitudes alimentaires des Bretons : bonnes ou mauvaises comparé au reste de la France ?'
author: Blogueur Invité
post_excerpt: ""
layout: post
permalink: >
  http://data-bzh.fr/habitudes-alimentaires-bretons-bonnes-mauvaises-compare-reste-de-france/
published: true
post_date: 2017-04-25 14:00:35
---
<h2>Les Bretons sont très attachés à leurs traditions alimentaires : kouign-amann, crêpes, cidre et autres spécialités... souvent à base de beurre ! Mais qu’en est-il de la réalité ? Existe-t-il encore aujourd’hui des habitudes spécifiques aux Bretons ? Et du point de vue de la santé, où se classe la Bretagne par rapport aux autres régions françaises en termes de « malbouffe » ?</h2>
<!--more-->

<em>Note : ce billet de blog invité a été rédigé par des étudiants en statistiques de l’ENSAE, faisant suite à leur <a href="https://frenchmalbouffetour.github.io">projet de dataviz</a> sur la malbouffe en France.</em>

[Tweet "#Bretagne — Les bretons et la malbouffe"]
<h3>Données</h3>
Les données ont été collectées à partir de 3 sources, toutes fournissant les résultats les plus récents sur le sujet :
<ul>
 	<li><a href="https://www.data.gouv.fr/fr/datasets/donnees-de-consommations-et-habitudes-alimentaires-de-letude-inca-2-3/" target="_blank" rel="noopener noreferrer">Enquête INCA 2 de l’ANSES sur les habitudes alimentaires des français (2007)</a></li>
 	<li><a href="http://www.roche.fr/content/dam/roche_france/fr_FR/doc/obepi_2012.pdf" target="_blank" rel="noopener noreferrer">Enquête ObEpi de l’INSERM sur l’obésité en France (2012)</a></li>
 	<li><a href="http://inpes.santepubliquefrance.fr/CFESBases/catalogue/pdf/1479.pdf" target="_blank" rel="noopener noreferrer">Enquête Baromètre santé de l’Inpes (2010) </a></li>
</ul>
Vous constaterez que le jeu de données INCA 2 est très riche : de nombreux datasets sont disponibles. Ceci est lié à la façon dont s’est déroulée l’enquête : <strong>chaque personne interrogée a dû remplir un « carnet de consommation »</strong> précis pendant en général 7 jours consécutifs. Nous avons donc accès à des informations très fines !

Ont été utilisées ici la table « INDIV » qui répertorie les réponses des individus interrogés à différentes questions sur leurs<strong> habitudes alimentaires</strong> et la table « CONSO » qui répertorie de façon agrégée les <strong>quantités consommées de plusieurs types d’aliments</strong> (Pain, Beurre, Lait, Pâtisseries etc) au cours de l’étude.

Notons que <strong>les enfants ont été écartés de l’analyse présentée ici</strong>, et que l’étude a été réalisée à plusieurs moments de l’année pour tenir compte de l’influence des saisons sur les habitudes alimentaires.
<h3>Analyse exploratoire</h3>
<h4>Le beurre et les Bretons</h4>
<a href="http://data-bzh.fr/wp-content/uploads/2017/04/DATABZH1-BEURRE.png"><img class="aligncenter size-full wp-image-3336" src="http://data-bzh.fr/wp-content/uploads/2017/04/DATABZH1-BEURRE.png" alt="beurre et breton" width="1200" height="600" /></a>

Comme on peut le constater sur la carte ci-dessus, l’amour de Bretons pour le beurre n’est pas un mythe ! <strong>La Bretagne est la région qui consomme le plus de beurre quotidiennement en France</strong>, avec une moyenne déclarée de 19g/jour. Ceci correspond à 50% de plus que la moyenne française (qui tient pourtant aussi compte des Bretons !) !

Vous noterez aussi en visitant <a href="https://frenchmalbouffetour.github.io/" target="_blank" rel="noopener noreferrer">French Malbouffe Tour</a> que la <strong>2ème</strong> région la plus consommatrice de beurre ne se situe pas très loin : il s’agit du<strong> Pays de la Loire</strong>, avec une consommation moyenne nette de 15g/jour !
<h4>L’alcool et les Bretons</h4>
<a href="http://data-bzh.fr/wp-content/uploads/2017/04/DATABZH2-ALCOOL.png"><img class="aligncenter size-full wp-image-3337" src="http://data-bzh.fr/wp-content/uploads/2017/04/DATABZH2-ALCOOL.png" alt="bretons et alcool 1" width="1200" height="600" /></a>

Beaucoup de clichés circulent sur l’alcool et les Bretons, et vous verrez ici qu’ils ne sont pas si faux… mais pas si vrais non plus !

Les <strong>Bretons sont effectivement premiers en ce qui concerne les ivresses répétées</strong>. Ceci signifie que c’est la région ayant le plus haut pourcentage de personnes ayant eu une ivresse répétées (au moins 3 fois) au cours de l’année.

Si vous consultez l’Atlas des usages de substances psychoactives issu du <a href="http://inpes.santepubliquefrance.fr/CFESBases/catalogue/pdf/1479.pdf" target="_blank" rel="noopener noreferrer">Baromètre santé de l’Inpes</a>, vous constaterez néanmoins que si les Bretons n’hésitent pas à s’enivrer, <strong>ce n’est absolument pas la région qui comporte le plus de personnes ayant un usage à risque chronique ou de dépendance de l’alcool</strong>. Ce problème concerne plutôt les régions du Sud de la France Midi-Pyrénées et Languedoc-Roussillon, ainsi que le Pays de la Loire.

Vous pouvez le voir sur cette carte « bonus » :

<a href="http://data-bzh.fr/wp-content/uploads/2017/04/DATABZH2BIS-ALCOOL.png"><img class="aligncenter size-full wp-image-3338" src="http://data-bzh.fr/wp-content/uploads/2017/04/DATABZH2BIS-ALCOOL.png" alt="Bretons et alcool bis" width="1200" height="600" /></a>
<h4>Les pâtisseries et les Bretons</h4>
<a href="http://data-bzh.fr/wp-content/uploads/2017/04/DATABZH3-PATISSERIES.png"><img class="aligncenter size-full wp-image-3339" src="http://data-bzh.fr/wp-content/uploads/2017/04/DATABZH3-PATISSERIES.png" alt="Bretons et patisseries" width="1200" height="600" /></a>

Est-ce lié au Kouign Amann ou non, <strong>les Bretons restent en tout cas relativement gourmands comparé au reste de la France</strong>. Ils se classent 3ème plus gros consommateurs de pâtisseries, avec une consommation moyenne de 56g/jour. A titre de comparaison, la Haute-Normandie consomme 39g/jour.
<h4>Les fruits et légumes et les Bretons</h4>
<a href="http://data-bzh.fr/wp-content/uploads/2017/04/DATABZH4-LEGUMES.png"><img class="aligncenter size-full wp-image-3340" src="http://data-bzh.fr/wp-content/uploads/2017/04/DATABZH4-LEGUMES.png" alt="Bretons fruits et légumes" width="1200" height="600" /></a>

Après tous ces aliments gras et sucrés, regardons maintenant du côté des aliments « bons pour la santé ». <strong>Si les Bretons consomment peut-être un peu trop de beurre, ils n’en restent pas moins des gros consommateurs de fruits et légumes</strong>.

Obésité, Sport, Charcuterie… : vous pouvez consulter où se classe la Bretagne sur ces autres critères directement sur le <a href="https://frenchmalbouffetour.github.io/" target="_blank" rel="noopener noreferrer">site du projet</a> — et aller découvrir les autres régions !
<h3>Informations complémentaires</h3>
<h4>Technologies utilisées :</h4>
<div><i>Analyse</i> : Python, et en particulier la librairie Pandas</div>
<div><i>Visualisation / Carte</i> : d3.js</div>
<div><i>Site web</i> : HTML / CSS / JavaScript et Bootstrap</div>
<h4>Github du projet :</h4>
<a href="https://github.com/frenchmalbouffetour/frenchmalbouffetour.github.io" target="_blank" rel="noopener noreferrer">Github du projet</a>
<h4>Etudiants à l’origine du projet :</h4>
Romane Persch – <a href="https://www.linkedin.com/in/romane-persch-73473b7b/" target="_blank" rel="noopener noreferrer">LinkedIn</a>
Thomas Seleck – <a href="https://www.linkedin.com/in/thomasseleck/" target="_blank" rel="noopener noreferrer">LinkedIn</a>
Guillaume Perigaud – <a href="https://www.linkedin.com/in/guillaumeperigaud/">LinkedIn</a>
Hicham Reghay – <a href="https://www.linkedin.com/in/hicham-reghay-659202a/" target="_blank" rel="noopener noreferrer">LinkedIn</a>