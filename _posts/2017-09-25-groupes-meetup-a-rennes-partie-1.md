---
ID: 3713
post_title: 'Groupes Meetup à Rennes &#8211; Partie 1'
author: Michel Caradec
post_excerpt: ""
layout: post
permalink: >
  http://data-bzh.fr/groupes-meetup-a-rennes-partie-1/
published: true
post_date: 2017-09-25 18:30:32
---
<h2>A une époque encore récente, toutes personnes partageant les mêmes centres d’intérêts passaient généralement par des structures comme des clubs, des centres culturels ou des associations afin de se rencontrer et d’échanger sur leurs passions communes.</h2>
<!--more-->
[Tweet "Les Groupes #Meetup de #Rennes en #Dataviz"]

L’avènement du smartphone et des réseaux sociaux a facilité ce processus de rencontre grâce à l’émergence de plateformes dédiées.

<strong><a href="https://www.meetup.com">Meetup</a></strong> est l’une d’entre elles, permettant à des personnes ayant les mêmes passions et vivant dans un même lieu de s’identifier et de se retrouver dans le cadre de rencontres organisées à l’initiative des créateurs des groupes (pour plus d’information, consulter la <a href="https://fr.wikipedia.org/wiki/Meetup.com">fiche Wikipedia</a>).

Dans cette série d’articles, nous allons étudier les groupes Meetup de la <strong>région de Rennes</strong>.
<div id="donnees" class="section level2">
<h2>Données</h2>
Comme toute plateforme souhaitant dynamiser son activité, Meetup propose une <a href="https://www.meetup.com/fr-FR/meetup_api/">interface de programmation</a> (ou <a href="https://fr.wikipedia.org/wiki/Interface_de_programmation">API</a>) permettant d’effectuer programmatiquement diverses opérations.

Dans le cadre de notre exploration, nous allons utiliser les fonctions suivantes :
<ul>
 	<li><a href="https://www.meetup.com/meetup_api/docs/find/groups/">Find Groups</a> : permet de récupérer une liste de groupes selon divers critères. Dans notre cas, nous utiliserons une sélection par géolocalisation.</li>
 	<li><a href="https://www.meetup.com/meetup_api/docs/2/members/">Members</a> : permet de récupérer les membres d’un groupe.</li>
</ul>
<em>L’accès à l’API étant ouvert (il suffit simplement d’avoir un compte Meetup et de demander une clé d’API), toute utilisation intensive est sanctionnée par un déni de réponse. Il faut donc modérer l’envoi de requêtes groupées en s’appuyant sur les <a href="https://www.meetup.com/meetup_api/docs/#limits">informations retournées par l’API</a>. <a href="http://www.twitter.com/_colinfay">Colin</a> a écrit un <a href="http://colinfay.me/rstats-api-calls-and-sys-sleep/">article sur le sujet</a>.</em>

Notre étude portera sur les groupes situés à <strong>Rennes</strong>, dans la limite d’un <strong>périmètre de 11 km</strong> (soit environ 7 miles, qui est l’unité de mesure utilisée par l’API).

Les données traitées dans cet article ont été collectées le <strong>24/09/2017</strong>. L’exactitude des chiffres n’est donc garantie qu’à cette date, du fait de l’évolution constante du réseau social.

</div>
<div id="analyse-exploratoire" class="section level2">
<h2>Analyse exploratoire</h2>
<div id="les-groupes" class="section level3">
<h3>Les groupes</h3>
Le nombre de groupes Meetup est de <strong>106</strong>.

Commençons par l’étude des groupes en fonction de leurs membres.

<img class="aligncenter size-full wp-image-3715" src="http://data-bzh.fr/wp-content/uploads/2017/09/01-group_size.png" alt="Popularité des groupes" width="1200" height="600" />

C’est le groupe <strong>Meetup La French Tech Rennes St Malo</strong> qui a le plus grand nombre de membres (<strong>1 249</strong>).

Un groupe populaire ne signifie pas qu’il est actif (à savoir qu’il propose un grand nombre d’évènements). La visualisation suivante énumère les groupes ayant organisé au moins un évènement <strong>depuis le 1er septembre 2017</strong>.

<img class="aligncenter size-full wp-image-3716" src="http://data-bzh.fr/wp-content/uploads/2017/09/02-group_last_event.png" alt="Activité des groupes" width="1200" height="600" />
<h3>Les membres</h3>
On comptabilise un total de <strong>6 611</strong> personnes distinctes (membres) inscrites à au moins un groupe.

Même si cet article ne traite que des <strong>groupes rennais</strong>, les membres peuvent-être originaires de différents coins du monde, comme le montre la carte suivante.

<img class="aligncenter size-full wp-image-3717" src="http://data-bzh.fr/wp-content/uploads/2017/09/03-member_world_map.png" alt="Membres dans le monde" width="1200" height="600" />

Ce phénomène reste néanmoins mineur, la plus grande partie des membres se trouvant à proximité du périmètre des groupes.

<img class="aligncenter size-full wp-image-3718" src="http://data-bzh.fr/wp-content/uploads/2017/09/04-member_city_hist.png" alt="Membres à Rennes" width="1200" height="600" />

De nombreux membres sont aussi localisés dans le reste de la Bretagne.

<img class="aligncenter size-full wp-image-3719" src="http://data-bzh.fr/wp-content/uploads/2017/09/05-member_bzh_map.png" alt="Membres en Bretagne" width="1200" height="600" />

Le nuage de points suivant, croisant tous les groupes avec tous les membres permet d'observer à un niveau global la répartition des affectations.

<img class="aligncenter size-full wp-image-3720" src="http://data-bzh.fr/wp-content/uploads/2017/09/06-member_heatmap.png" alt="Groupes &amp; membres" width="1200" height="600" />
<div id="les-membres" class="section level3">

Les alignements horizontaux les plus denses correspondent aux groupes avec le plus grand nombre de membres. On devine les groupes les plus populaires précédemment évoqués.

Les alignements verticaux, correspondant aux membres présents dans un grand nombre de groupes, sont beaucoup plus difficilement identifiables. Rares sont en effet les personnes inscrites à l'ensemble des groupes…

</div>
<div id="les-themes" class="section level3">
<h3>Les thèmes</h3>
Chaque groupe possède une ou plusieurs thématiques (les “topics”) permettant leur qualification et facilitant leur recherche. Pour les groupes rennais, pas moins de <strong>560</strong> thèmes sont référencés.

Le graphique ci-dessous met en évidence les <strong>20 thèmes</strong> les plus fréquents.

<img class="aligncenter size-full wp-image-3721" src="http://data-bzh.fr/wp-content/uploads/2017/09/07-topic_count.png" alt="20 thèmes les plus populaires" width="1200" height="600" />

C’est le thème <strong>Entrepreneurship</strong>, suivi du thème <strong>New Technology</strong> que l’on retrouve le plus souvent.

Le nuage de points suivant, croisant tous les groupes avec tous les thèmes permet d’observer à un niveau global la répartition des affectations.

<img class="aligncenter size-full wp-image-3722" src="http://data-bzh.fr/wp-content/uploads/2017/09/08-topic_heatmap.png" alt="Groupes &amp; thèmes" width="1200" height="600" />
<div id="analyse-exploratoire" class="section level2">
<div id="les-themes" class="section level3">

L’alignement horizontal ou vertical des points indique dans quelle mesure un même thème est associé à plusieurs groupes, ou un même groupe possède plusieurs thèmes.

</div>
</div>
<div id="conclusion" class="section level2">
<h2>Conclusion</h2>
Ainsi s’achève la première partie de notre série sur les <strong>meetups rennais</strong>. Dans un prochain article, nous poursuivrons l’exploration de nos données en utilisant un autre type de visualisation.

Et en attendant, n’hésitez pas à vous inscrire aux Meetups traitant de la données (liste non-exhaustive) :
<ul>
 	<li><a href="https://www.meetup.com/Rennes-Data-Club/">Rennes Data Club</a>.</li>
 	<li><a href="https://www.meetup.com/Meetup-Machine-Learning-Rennes/">Machine Learning Rennes</a>.</li>
 	<li><a href="https://www.meetup.com/Data2Breakfast/">Data2Breakfast</a>.</li>
 	<li><a href="https://www.meetup.com/Hadoop-User-Group-Grand-Ouest/">Hadoop User Group Grand Ouest</a>.</li>
</ul>
&nbsp;

</div>
</div>
</div>
</div>