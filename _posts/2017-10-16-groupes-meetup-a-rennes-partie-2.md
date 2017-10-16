---
ID: 3782
post_title: 'Groupes Meetup à Rennes &#8211; Partie 2'
author: Michel Caradec
post_excerpt: ""
layout: post
permalink: >
  http://data-bzh.fr/groupes-meetup-a-rennes-partie-2/
published: true
post_date: 2017-10-16 18:00:45
---
<h2>Dans le <a href="http://data-bzh.fr/groupes-meetup-a-rennes-partie-1/">précédent article</a>, nous avons exploré les <strong>meetups rennais</strong> en utilisant les outils classiques de visualisation de données (nuages de points, diagrammes en barres, cartographie).</h2>
<!--more-->[Tweet "Les Groupes #Meetup de #Rennes en #Dataviz - Partie 2"]

L’organisation des données collectées, constituant une structure en réseau (des membres de groupes qualifiés par des thèmes), nous permet d’utiliser des outils d’analyse plus avancés que sont les <strong>bases de données orientées graphes</strong>.
Dans cet article, nous allons découvrir comment les <strong>graphes</strong> et les visualisations associées permettent d’appréhender les données d’une façon différente.
<div id="donnees" class="section level2">
<h2>Données</h2>
Les données ont été collectées via l’<a href="https://www.meetup.com/fr-FR/meetup_api/">interface de programmation</a> (ou <a href="https://fr.wikipedia.org/wiki/Interface_de_programmation">API</a>) mise à disposition par <strong><a href="https://www.meetup.com">Meetup</a></strong>, et portent sur les groupes situés à <strong>Rennes</strong>, dans la limite d’un <strong>périmètre de 11 km</strong>, à la date du <strong>24/09/2017</strong>.

</div>
<div id="quelques-notions-de-graphes" class="section level2">
<h2>Quelques notions de Graphes</h2>
Les données d’une <a href="https://fr.wikipedia.org/wiki/Base_de_données_orientée_graphe">base de données orientée graphes</a> sont stockées selon le principe de la <a href="https://fr.wikipedia.org/wiki/Théorie_des_graphes">théorie des graphes</a>.

Les entités, représentées par des <strong>noeuds</strong> (nodes, vertices), sont reliées par des <strong>arcs</strong> (edges, links). Ceci permet une représentation de l’information moins technique, plus concrète.

La visualisation suivante est un exemple de la représentation en graphe :

<img class="aligncenter size-full wp-image-3770" src="http://data-bzh.fr/wp-content/uploads/2017/10/00-graph.exemple.png" alt="Exemple de graphe" width="1200" height="600" />
<div id="quelques-notions-de-graphes" class="section level2">

<em>Les noeuds (en rouge et vert pour les personnes) représentent des sujets, les arcs expriment un fait sous la forme d’un verbe. La taille des noeuds est proportionnelle au nombre d’arcs qu’ils ont.</em>

</div>
<div id="analyse-exploratoire" class="section level2">
<h2>Analyse exploratoire</h2>
<div id="groupes-et-membres" class="section level3">
<h3>Groupes et membres</h3>
Commençons par l’exploration des groupes et de leurs membres.

<img class="aligncenter size-full wp-image-3771" src="http://data-bzh.fr/wp-content/uploads/2017/10/01-member.to_.group_.png" alt="Groupes et membres" width="1200" height="600" />

<em>Les groupes sont en rouge, le membres sont en vert, la taille des groupes est proportionnelle au nombre de membres qu’ils ont (on parle de <strong><a href="https://fr.wikipedia.org/wiki/Degré_(théorie_des_graphes)">degré</a></strong>).</em>

Plus les membres sont positionnés au centre, plus ils sont inscrits à un grand nombre de groupes. A contrario, les membres positionnés vers l’extérieur sont inscrits dans peu de groupes (un seul s’ils se trouvent en périphérie).

Si l’on peut éventuellement apprécier le caractère artistique d’une telle visualisation, l’information qu’elle apporte reste difficilement exploitable, du fait du grand nombre de noeuds (membres et groupes = <strong>6 714</strong>) et de liens (<strong>23 138</strong>) à faire figurer dans l’espace limité de cet article (notre charte graphique imposant une taille d'image de 1200 * 600 pixels).

Il est plus approprié dans ce cas de faire appel à une visualisation dynamique, permettant de naviguer dans le graphe au gré de ses investigations. Un exemple (réalisé à partir de nos données avec l'outil <a href="https://gephi.org"><strong>Gephi</strong></a> et l'extension <a href="https://gephi.org/plugins/#/plugin/sigmaexporter"><strong>SigmaExporter</strong></a>) est consultable en suivant <a href="https://michelcaradec.github.io/MeetupRennes/member_to_group/index.html">ce lien</a>.

Le graphe précédent contenait <strong>2 types de noeuds</strong> : les <strong>groupes</strong> et les <strong>membres</strong>. On parle dans ce cas de <strong><a href="https://fr.wikipedia.org/wiki/Graphe_biparti">graphe biparti</a></strong>. Il est possible à partir de ce graphe de déduire 2 graphes <strong>monopartis</strong> (on parle de <strong><a href="https://en.wikipedia.org/wiki/Bipartite_network_projection">projection</a></strong>) :
<ul>
 	<li>1 graphe dont les noeuds représentent les <strong>groupes</strong>, et les liens le nombre de <strong>membres en commun</strong> entre chaque groupe.</li>
 	<li>1 graphe dont les noeuds représentent les <strong>membres</strong>, et les liens le nombre de <strong>groupes en commun</strong> entre chaque membre.</li>
</ul>
Etudions la projection des <strong>groupes</strong> liés par rapport aux <strong>membres</strong> qu’ils ont en commun (pour des raisons de performance, la projection des membres ne sera pas évoquée dans cet article).

<img class="aligncenter size-full wp-image-3772" src="http://data-bzh.fr/wp-content/uploads/2017/10/02-group.to_.group_.via_.member.png" alt="Groupes liés par leurs membres" width="1200" height="600" />

<em>Les groupes sont en rouge, la taille des groupes est proportionnelle au nombre de groupes auxquels ils sont connectés.</em>

La densité de ce graphe illustre les nombreuses connexions entre les groupes. Une personne est effet généralement membre de plusieurs groupes.

C’est entre le groupe <strong>Le Shift</strong> et <strong>La Cordée Rennes - partage, événements et bonne humeur</strong> que l’on observe le lien le plus fort, avec <strong>461</strong> membres en commun.

Le tableau suivant énumère les <strong>10</strong> couples de groupes avec le plus fort lien :
<table>
<thead>
<tr>
<th align="left">Groupe 1</th>
<th align="left">Groupe 2</th>
<th align="right">Membres en commun</th>
</tr>
</thead>
<tbody>
<tr>
<td align="left">Le Shift</td>
<td align="left">La Cordée Rennes - partage, événements et bonne humeur</td>
<td align="right">461</td>
</tr>
<tr>
<td align="left">Le Shift</td>
<td align="left">Meetup La French Tech Rennes St Malo</td>
<td align="right">456</td>
</tr>
<tr>
<td align="left">La Cordée Rennes - partage, événements et bonne humeur</td>
<td align="left">Meetup La French Tech Rennes St Malo</td>
<td align="right">447</td>
</tr>
<tr>
<td align="left">UX Rennes</td>
<td align="left">Meetup La French Tech Rennes St Malo</td>
<td align="right">404</td>
</tr>
<tr>
<td align="left">UX Rennes</td>
<td align="left">Le Shift</td>
<td align="right">390</td>
</tr>
<tr>
<td align="left">Agile Rennes</td>
<td align="left">UX Rennes</td>
<td align="right">361</td>
</tr>
<tr>
<td align="left">DevCamp Rennes</td>
<td align="left">RennesJS</td>
<td align="right">352</td>
</tr>
<tr>
<td align="left">UX Rennes</td>
<td align="left">La Cordée Rennes - partage, événements et bonne humeur</td>
<td align="right">352</td>
</tr>
<tr>
<td align="left">Docker Rennes</td>
<td align="left">Rennes devops</td>
<td align="right">350</td>
</tr>
<tr>
<td align="left">Agile Rennes</td>
<td align="left">Osons le Leadership Rennes</td>
<td align="right">346</td>
</tr>
</tbody>
</table>
La même information peut bien entendu être restituée sous la forme d’un graphe :

<img class="aligncenter size-full wp-image-3773" src="http://data-bzh.fr/wp-content/uploads/2017/10/03-group.to_.group_.via_.member.top_.png" alt="Groupes les plus fortement liés par leurs membres" width="1200" height="600" />

<em>Les groupes sont en rouge, les nombres sur les liens indiquent le nombre de membres en commun.</em>

On observe qu’il existe une interaction parfois importante entre les membres des groupes. A l’extrême, on aura une situation où les mêmes personnes seront inscrites aux mêmes groupes, créant ainsi un <strong>entre-soi</strong>.

Quelle est l’importance de ce phénomène pour les groupes de notre jeu de données ?

<img class="aligncenter size-full wp-image-3774" src="http://data-bzh.fr/wp-content/uploads/2017/10/04-group.to_.group_.via_.member.cluster.png" alt="Communautés de groupes liés par leurs membres" width="1200" height="600" />

<em>Les groupes sont colorés en fonction de leur appartenance à une même communauté, la taille des groupes est proportionnelle au nombre de groupes auxquels ils sont connectés.</em>

Les communautés, au nombre de <strong>4</strong>, ont été détectées selon la méthode du <strong>walktrap</strong>.

<em>La méthode du <strong>walktrap</strong> consiste à identifier des sous-graphes fortement connectés en navigant aléatoirement de noeuds en noeuds, en partant du principe que le déplacement aléatoire aura tendance à rester à l’intérieur de la communauté plutôt que de la quitter.</em>

Notre attention est attirée par un groupe isolé dans sa propre communauté (de couleur jaune). Il s’agit du Meetup <strong>Communauté vidéo iPhone Bretagne</strong>. Cette mise à l’écart s’explique par le fait que ce groupe n’est composé que de <strong>1</strong> membre (à l’évidence son créateur).
<h3>Groupes et thèmes</h3>
Passons à l’exploration des groupes et de leurs thèmes.

Le graphique ci-dessous permet de visualiser le <strong>réseau</strong> constitué par les groupes et leurs thématiques (un même thème pouvant être partagé avec plusieurs groupes).

<img class="aligncenter size-full wp-image-3775" src="http://data-bzh.fr/wp-content/uploads/2017/10/05-topic.to_.group_.png" alt="Groupes et thèmes" width="1200" height="600" />

<em>Les groupes sont en rouge, les thèmes sont en vert, la taille des groupes est proportionnelle au nombre de thèmes auxquels ils sont connectés.</em>

Il y a <strong>106</strong> groupes pour <strong>560</strong> thèmes.

Le groupe avec le plus grand nombre de thèmes est <strong>Docker Rennes</strong>, avec les thèmes <strong>Linux, Cloud Computing, Open Source, Big Data, Configuration Management, Operations and Data Center Management, Data Center and Operations Automation, DevOps, IaaS (Infrastructure as a Service), PaaS (Platform as a Service), Cloud Security, Virtualization, Infrastructure as Code, OpenStack, Continuous Delivery, Docker</strong>.

On observe que certains groupes sont <strong>isolés</strong>, c’est à dire qu’ils ne sont reliés à aucun autres groupes par l’intermédiaire de leurs thèmes (les thèmes étant de fait eux aussi isolés). Ces groupes sont <strong>WineRennes - Passion du vin, Neurofeedback Rennes, Meetup Photographie Pro (Rennes), Convention et séminaire chrétien</strong>.

<img class="aligncenter size-full wp-image-3776" src="http://data-bzh.fr/wp-content/uploads/2017/10/06-topic.to_.group_.isolated.png" alt="Groupes et thèmes isolés" width="1200" height="600" />

<em>Les groupes sont en rouge, les thèmes sont en vert.</em>

Comme nous l’avons précédemment fait pour les groupes et leurs membres, étudions la projection des <strong>groupes</strong> liés par rapport aux <strong>thèmes </strong>qu’ils ont en commun.

<img class="aligncenter size-full wp-image-3777" src="http://data-bzh.fr/wp-content/uploads/2017/10/07-group.to_.group_.via_.topic_.png" alt="Groupes liés par leurs thèmes" width="1200" height="600" />

<em>Les groupes sont en rouge, la taille des groupes est proportionnelle au nombre de groupes auxquels ils sont connectés.</em>

On retrouve sur cette visualisation les groupes isolés par leurs thèmes précédemment évoqués.

Poursuivons avec la projection des <strong>thèmes</strong> liés par rapport aux <strong>groupes</strong> qu’ils ont en commun.

<img class="aligncenter size-full wp-image-3778" src="http://data-bzh.fr/wp-content/uploads/2017/10/08-topic.to_.topic_.via_.group_.png" alt="Thèmes liés par leurs groupes" width="1200" height="600" />

<em>Les thèmes sont en rouge, la taille des thèmes est proportionnelle au nombre de thèmes auxquels ils sont connectés.</em>

Les ensembles isolés matérialisent les thèmes des groupes isolés.
<h3>Zoom sur les groupes Data</h3>
Notre étude a jusqu’à présent porté sur l’ensemble de la communauté Meetup rennaise.

Terminons avec un sous-ensemble de notre communauté, dédié aux <strong>Meetups traitant de la données</strong> que sont <a href="https://www.meetup.com/Rennes-Data-Club/">Rennes Data Club</a>, <a href="https://www.meetup.com/Meetup-Machine-Learning-Rennes/">Machine Learning Rennes</a> et <a href="https://www.meetup.com/Data2Breakfast/">Data2Breakfast</a>.

<img class="aligncenter size-full wp-image-3779" src="http://data-bzh.fr/wp-content/uploads/2017/10/09-member.to_.group_.data_.png" alt="Groupes Data et leurs membres" width="1200" height="600" />

<em>Les groupes sont en rouge, les membres sont en vert, la taille des groupes est proportionnelle au nombre de membres auxquels ils sont connectés.</em>

On visualise clairement les membres communs à 2, voire 3 groupes.

Les plus attentifs auront remarqué un cercle jaune noyé au milieu du graphe, représentant un membre dont ils n’auront aucun mal à deviner l’identité. ;-)

Si l’on applique une segmentation (toujours selon la méthode du <strong>walktrap</strong>), on constate que le groupe <strong>Meetup Machine Learning Rennes</strong> se démarque des autres groupes, du moins du point de vue des connexions de ses membres avec les autres groupes…

<img class="aligncenter size-full wp-image-3780" src="http://data-bzh.fr/wp-content/uploads/2017/10/10-member.to_.group_.data_.cluster.png" alt="Communautés des groupes Data et leurs membres" width="1200" height="600" />
<div id="analyse-exploratoire" class="section level2">
<div id="zoom-sur-les-groupes-data" class="section level3">

<em>Les groupes et membres sont colorés en fonction de leur appartenance à une même communauté, la taille des groupes est proportionnelle au nombre de membres auxquels ils sont connectés.</em>

</div>
</div>
<div id="conclusion" class="section level2">
<h2>Conclusion</h2>
Les possibilités offertes par les visualisations en graphes n’ont de limite que notre imagination. Nous nous arrêterons à ce stade en ce qui concerne cet article.

Dans un prochain article, nous nous intéresserons aux moyens d’interroger les données sous forme de graphes.

</div>
</div>
</div>
</div>