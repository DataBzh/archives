---
ID: 3816
post_title: 'Groupes Meetup à Rennes &#8211; Partie 3 (Neo4j)'
author: Michel Caradec
post_excerpt: ""
layout: post
permalink: >
  http://data-bzh.fr/groupes-meetup-a-rennes-partie-3-neo4j/
published: true
post_date: 2017-11-05 18:00:02
---
<h2>Dans le <a href="http://data-bzh.fr/groupes-meetup-a-rennes-partie-2/">précédent article</a>, nous avons exploré les <strong>Meetups rennais</strong> à l’aide de visualisations restituant les données sous forme de graphes.</h2>
<!--more-->[Tweet "Groupes #Meetup #Rennes #Neo4j #Graph #Cypher"]

Pour ce faire, nous nous sommes appuyés sur la capacité des librairies <strong><a href="https://cran.r-project.org/package=igraph">igraph</a></strong> et <strong><a href="https://cran.r-project.org/package=ggraph">ggraph</a></strong> du langage <strong><a href="https://www.r-project.org/">R</a></strong>, qui proposent de nombreuses fonctionnalités à partir de l’interface standard de manipulation des données que sont les <strong><a href="http://www.r-tutor.com/r-introduction/data-frame">data frames</a></strong> (impliquant une représentation tabulaire de l’information).

Dans cet article, nous allons utiliser <strong><a href="https://neo4j.com/">Neo4j</a></strong>, un moteur de bases de données orientées graphes, et découvrir comment ce type de technologie peut-être utilisé pour exploiter nos données.
<h2>Données</h2>
Les données ont été collectées via l’<a href="https://www.meetup.com/fr-FR/meetup_api/">interface de programmation</a> (ou <a href="https://fr.wikipedia.org/wiki/Interface_de_programmation">API</a>) mise à disposition par <strong><a href="https://www.meetup.com">Meetup</a></strong>, et portent sur les groupes situés à <strong>Rennes</strong>, dans la limite d’un <strong>périmètre de 11 km</strong>, à la date du <strong>24/09/2017</strong>.
<h2>Neo4j</h2>
Contrairement à un système de gestion de bases de données relationnelles, qui stocke les données dans des <strong>tables</strong> sous forme de lignes et de colonnes (avec éventuellement des relations entre les tables), Neo4j stocke les données dans un format non structuré, en les organisant par rapport à leurs <strong>connexions</strong>. Ceci permet de conserver des performances quasi-constantes lors de requêtes multi-niveaux (impliquants des relations en cascade), même lorsque le volume de données augmente.

Un langage de manipulation dédié, <strong><a href="https://neo4j.com/developer/cypher/">Cypher</a></strong>, permet d’exprimer des requêtes de façon intuitive.

Ces deux atouts font des bases de données orientées graphes en général, et de Neo4j en particulier, un outil fort adapté pour l’analyse de structures en réseau, comme les réseaux sociaux, les parcs informatiques (avec des services dépendants les uns des autres), ou les réseaux criminels (détection de fraudes).
<h3>Distribution</h3>
Au moment de la rédaction de cet article, la version de Neo4j est la <strong>3.3.0</strong>. Une <a href="https://neo4j.com/download/other-releases/">édition communautaire</a> (Neo4j Community Edition) peut-être installée sous environnement Linux, Mac ou Windows, et permet de rapidement expérimenter.

Neo4j peut-être exploité via différentes interfaces :
<ul>
 	<li>Un <strong>shell</strong> en ligne de commande : <strong>Cypher-shell</strong>.</li>
 	<li>Un navigateur : <strong>Neo4j Browser</strong>.</li>
 	<li>Des <strong>APIs</strong> (pour Java, Python, C#, R, etc.).</li>
 	<li>Des outils dédiés comme <strong><a href="https://linkurio.us/">Linkurious</a></strong>, qui a été utilisé dans le cadre des <strong><a href="https://panamapapers.icij.org/">Panama Papers</a></strong>.</li>
</ul>
Nous utiliserons les 3 premiers outils pour manipuler nos données.
<h2>Création de la base</h2>
<div id="base-exemple" class="section level3">
<h3>Base exemple</h3>
Dans le <a href="http://data-bzh.fr/groupes-meetup-a-rennes-partie-2/">précédent article</a>, nous avions introduit le concept de représentation de données sous la forme d’un graphe avec cet exemple :

<img class="aligncenter size-full wp-image-3770" src="http://data-bzh.fr/wp-content/uploads/2017/10/00-graph.exemple.png" alt="Exemple de graphe" width="1200" height="600" />

Si nous devions stocker ces informations dans une base de données SQL, nous pourrions utiliser le modèle physique suivant :

<img class="aligncenter size-full wp-image-3819" src="http://data-bzh.fr/wp-content/uploads/2017/11/Data-Bzh-Sample-MPD.png" alt="Data-Bzh Sample MPD" width="1200" height="600" />

L’alimentation des tables s’effectuerait à l’aide de commandes SQL de type INSERT, ordonnées comme il se doit afin de respecter les diverses contraintes d’intégrité fonctionnelles qui régissent les connexions entre les tables.

Avec le langage de manipulation <strong><a href="https://neo4j.com/developer/cypher/">Cypher</a></strong>, la création et l’alimentation de notre base exemple s’effectue de la façon suivante :
<pre><code>CREATE
  (a:Personne {nom: 'Colin'}),
  (b:Personne {nom: 'Michel'}),
  (c:Personne {nom: 'Tristan'}),
  (d:Site {nom: 'Data-Bzh'}),
  (e:Activite {nom: 'Trail'}),
  (f:Auteur {nom: 'Proust'}),
  (g:Langage {nom: 'R'}),
  (a)-[:EST_CREATEUR]-&gt;(d),
  (a)-[:EST_CONTRIBUTEUR]-&gt;(d),
  (a)-[:LIT]-&gt;(f),
  (a)-[:PROGRAMME_EN]-&gt;(g),
  (b)-[:EST_CONTRIBUTEUR]-&gt;(d),
  (b)-[:PRATIQUE]-&gt;(e),
  (b)-[:PROGRAMME_EN]-&gt;(g),
  (c)-[:EST_CONTRIBUTEUR]-&gt;(d),
  (c)-[:PROGRAMME_EN]-&gt;(g);</code></pre>
La première partie du script créé les noeuds. La seconde créé les relations entre les noeuds.

On constate que la où SQL requiert de créer une structure (relativement figée) organisée autour de tables, puis de les alimenter, Neo4j ne nécessite aucun schéma préalable. Il suffit simplement de déclarer les noeuds et relations selon un formalisme très visuel similaire à du <strong><a href="https://fr.wikipedia.org/wiki/Art_ASCII">ASCII Art</a></strong>, avec une structure de type <code>(noeud départ)-[:RELATION]-&gt;(noeud arrivée)</code>, les noeuds étant encadrés par des parenthèses, les relations par des crochets, le tout étant lié par des flèches, un peu comme ce que nous ferions si nous étions amenés à dessiner un schéma sur un tableau.

A noter que le noeuds peuvent-être regroupés par familles, grâce aux <strong>labels</strong> : <code>(:Personne)</code> représente un noeud avec le label “Personne”. Il est possible pour des noeuds de même label d’avoir des <strong>propriétés</strong> différentes, et pour un noeud d’avoir plusieurs labels.

Pour afficher l’ensemble des noeuds et relations, nous exécuterons la requête Cypher suivante :
<pre><code>MATCH (n) RETURN *;</code></pre>
<img class="aligncenter size-full wp-image-3818" src="http://data-bzh.fr/wp-content/uploads/2017/11/Data-Bzh-Graph-Sample.png" alt="Data-Bzh Graph Sample" width="1200" height="536" />

Vous pouvez retrouver ce graphe sur la <strong>console en ligne</strong> de Neo4j : <a class="uri" href="http://console.neo4j.org/r/l771u9">http://console.neo4j.org/r/l771u9</a>.
<h3>Base Meetup</h3>
Pour la base Meetup, nous allons utiliser l’import à partir de fichiers délimités (format <a href="https://fr.wikipedia.org/wiki/Comma-separated_values">CSV</a>).

Commençons par créer les <strong>noeuds</strong> :
<pre><code>// Création des groupes
// Fichier source : groups.nodes.tsv
// Structure : id, name, link, country, city, lon, lat, created, last_event
LOAD CSV WITH HEADERS
    FROM "file:///groups.nodes.tsv"
    AS row
    FIELDTERMINATOR '\t'
CREATE (:Group {id: toInteger(row.id), name: row.name, link:row.link, country:row.country, city:row.city, lon:toFloat(row.lon), lat:toFloat(row.lat), create:row.created, last_event:row.last_event});

// Création des thèmes
// Fichier source : topics.nodes.tsv
// Structure : id, name
LOAD CSV WITH HEADERS
    FROM "file:///topics.nodes.tsv"
    AS row
    FIELDTERMINATOR '\t'
CREATE (:Topic {id: toInteger(row.id), name: row.name});

// Création des membres
// Fichier source : members.nodes.tsv
// Structure : id, country, city, lon, lat
USING PERIODIC COMMIT 500
LOAD CSV WITH HEADERS
    FROM "file:///members.nodes.tsv"
    AS row
    FIELDTERMINATOR '\t'
CREATE (:Member {id: toInteger(row.id), country: row.country, city:row.city, lon:toFloat(row.lon), lat:toFloat(row.lat)});</code></pre>
Poursuivons avec la création des <strong>relations</strong>, qui permettront de connecter les différents noeuds :
<pre><code>// Relations entre groupes et thèmes
// Fichier source : topic_to_group.rel.tsv
// Structure : topic.id, group.id
USING PERIODIC COMMIT 500
LOAD CSV WITH HEADERS
    FROM "file:///topic_to_group.rel.tsv"
    AS row
    FIELDTERMINATOR '\t'
MATCH (t:Topic {id: toInteger(row.`topic.id`)})
MATCH (g:Group {id: toInteger(row.`group.id`)})
CREATE (g)-[:HAS_TOPIC]-&gt;(t);

// Relations entre groupes et membres
// Fichier source : member_to_group.rel.tsv
// Structure : group.id, member.id
USING PERIODIC COMMIT 500
LOAD CSV WITH HEADERS
    FROM "file:///member_to_group.rel.tsv"
    AS row
    FIELDTERMINATOR '\t'
MATCH (m:Member {id: toInteger(row.`member.id`)})
MATCH (g:Group {id: toInteger(row.`group.id`)})
CREATE (m)-[:IS_MEMBER]-&gt;(g);</code></pre>
La base de données graphe ainsi constituée a une taille d’environ <strong>23 Mo</strong>.

Les requêtes suivantes permettent de retourner quelques informations complémentaires.

Nombre total de membres :
<pre><code>MATCH (n:Member) RETURN COUNT(n) AS MemberCount;

+-------------+
| MemberCount |
+-------------+
| 6611        |
+-------------+</code></pre>
Nombre total de groupes :
<pre><code>MATCH (g:Group) RETURN COUNT(g) AS GroupCount;

+------------+
| GroupCount |
+------------+
| 108        |
+------------+</code></pre>
Nombre total de thèmes :
<pre><code>MATCH (t:Topic) RETURN COUNT(t) AS TopicCount;

+------------+
| TopicCount |
+------------+
| 560        |
+------------+</code></pre>
<h2>Interrogation</h2>
Le tableau suivant expose quelques requêtes permettant de se familiariser un peu plus avec Cypher :
<table class="table table-condensed"><colgroup> <col width="5%" /> <col width="5%" /> <col width="5%" /></colgroup>
<thead>
<tr class="header">
<th width="10%">#</th>
<th width="60%">Cypher</th>
<th width="30%">Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>1</td>
<td><code>MATCH (g:Group)-[:HAS_TOPIC]-&gt;(t:Topic) RETURN g, t</code></td>
<td>Tous les groupes et thèmes</td>
</tr>
<tr class="even">
<td>2</td>
<td><code>MATCH (g:Group) WHERE g.name CONTAINS "Data" RETURN *</code></td>
<td>Groupes dont le nom contient “Data”</td>
</tr>
<tr class="odd">
<td>3</td>
<td><code>MATCH (g1:Group)&lt;-[:IS_MEMBER]-(m:Member)-[:IS_MEMBER]-&gt;(g2:Group) WHERE g1 &lt;&gt; g2 RETURN DISTINCT g1.name, g2.name, COUNT(m) AS weight ORDER BY weight DESC LIMIT 10;</code></td>
<td>Paires de groupes ayant des membres en commun (avec le poids représentant le nombre de membres)</td>
</tr>
<tr class="even">
<td>4</td>
<td><code>MATCH (m:Member)-[r:IS_MEMBER]-&gt;(g:Group) RETURN g.name, COUNT(m) AS count ORDER BY count DESC;</code></td>
<td>Nombre de membres par groupe</td>
</tr>
<tr class="odd">
<td>5</td>
<td><code>MATCH (m:Member)-[:IS_MEMBER]-&gt;(g:Group) WITH m.id as id, COUNT(g) AS c RETURN MIN(c) AS min, MAX(c) AS max, AVG(c) AS avg;</code></td>
<td>Statistiques sur le nombre de groupes par membre</td>
</tr>
</tbody>
</table>
La saisie d’une requête depuis <strong>Neo4j Browser</strong> permet de bénéficier de l’auto-complétion et de la visualisation graphique du résultat :
<img class="aligncenter size-full wp-image-3817" src="http://data-bzh.fr/wp-content/uploads/2017/11/cypher_in_action-low.gif" alt="Cypher en action" width="1150" height="612" />
<h3>Interrogation avec R</h3>
Le package <strong>R</strong> <strong><a href="https://cran.r-project.org/package=RNeo4j">RNeo4j</a></strong> permet de manipuler les données Neo4j depuis notre environnement de prédilection.

La connexion au serveur s’effectue avec la fonction <strong><a href="https://www.rdocumentation.org/packages/RNeo4j/versions/1.6.4/topics/startGraph">startGraph</a></strong>.
<pre class="r"><code class="r"><span class="identifier">graph</span> <span class="operator">&lt;-</span> <span class="identifier">startGraph</span><span class="paren">(</span><span class="string">"http://localhost:7474/db/data/"</span>, <span class="identifier">username</span> <span class="operator">=</span> <span class="identifier">Neo4jUser</span>, <span class="identifier">password</span> <span class="operator">=</span> <span class="identifier">Neo4JPassword</span><span class="paren">)</span></code></pre>
Les requêtes <strong>Cypher</strong> sont exécutées avec les fonctions <strong><a href="https://www.rdocumentation.org/packages/RNeo4j/versions/1.6.4/topics/cypher">cypher</a></strong> ou <strong><a href="https://www.rdocumentation.org/packages/RNeo4j/versions/1.6.4/topics/cypherToList">cypherToList</a></strong>, selon que la requête retourne une structure tabulaire ou un sous-ensemble du graphe (composé de noeuds, relations ou chemins).

La requête suivante permet de récupérer (via la fonction <strong><a href="https://www.rdocumentation.org/packages/RNeo4j/versions/1.6.4/topics/cypher">cypher</a></strong>) les groupes ayant pour thème “Big Data” :
<pre class="r"><code class="r"><span class="identifier">df</span> <span class="operator">&lt;-</span> <span class="identifier">cypher</span><span class="paren">(</span><span class="identifier">graph</span>, <span class="string">"MATCH (g:Group)-[:HAS_TOPIC]-&gt;(:Topic {name: 'Big Data'}) RETURN g.name, g.last_event"</span><span class="paren">)</span>
<span class="identifier">names</span><span class="paren">(</span><span class="identifier">df</span><span class="paren">)</span> <span class="operator">&lt;-</span> <span class="identifier">c</span><span class="paren">(</span><span class="string">"name"</span>, <span class="string">"last_event"</span><span class="paren">)</span>
<span class="identifier">df</span></code></pre>
<table>
<thead>
<tr>
<th align="left">name</th>
<th align="left">last_event</th>
</tr>
</thead>
<tbody>
<tr>
<td align="left">Docker Rennes</td>
<td align="left">2017-09-13</td>
</tr>
<tr>
<td align="left">Meetup Machine Learning Rennes</td>
<td align="left">2017-09-12</td>
</tr>
<tr>
<td align="left">EXPAIR - Applications Connectées et Intelligentes</td>
<td align="left">2016-11-24</td>
</tr>
<tr>
<td align="left">Rennes Data Club</td>
<td align="left">2017-09-14</td>
</tr>
<tr>
<td align="left">Data2Breakfast</td>
<td align="left">2017-06-08</td>
</tr>
<tr>
<td align="left">NightClazz by Zenika Rennes</td>
<td align="left">2017-03-01</td>
</tr>
<tr>
<td align="left">Digital-Cloud GO (Grand Ouest) Meetup</td>
<td align="left">2017-01-26</td>
</tr>
</tbody>
</table>
La même requête avec la fonction <strong><a href="https://www.rdocumentation.org/packages/RNeo4j/versions/1.6.4/topics/cypherToList">cypherToList</a></strong> :
<pre class="r"><code class="r"><span class="identifier">res</span> <span class="operator">&lt;-</span> <span class="identifier">cypherToList</span><span class="paren">(</span><span class="identifier">graph</span>, <span class="string">"MATCH (g:Group)-[:HAS_TOPIC]-&gt;(:Topic {name: 'Big Data'}) RETURN g"</span><span class="paren">)</span>
<span class="identifier">df</span> <span class="operator">&lt;-</span> <span class="identifier">as.data.frame</span><span class="paren">(</span><span class="identifier">t</span><span class="paren">(</span><span class="identifier">sapply</span><span class="paren">(</span><span class="identifier">res</span>, <span class="keyword">function</span><span class="paren">(</span><span class="identifier">i</span><span class="paren">)</span> <span class="paren">{</span> <span class="identifier">unlist</span><span class="paren">(</span><span class="identifier">i</span><span class="operator">$</span><span class="identifier">g</span><span class="paren">)</span> <span class="paren">}</span><span class="paren">)</span><span class="paren">)</span><span class="paren">)</span>
<span class="identifier">df</span> <span class="operator">&lt;-</span> <span class="identifier">df</span><span class="paren">[</span>, <span class="identifier">c</span><span class="paren">(</span><span class="string">"name"</span>, <span class="string">"last_event"</span><span class="paren">)</span><span class="paren">]</span>
<span class="identifier">df</span></code></pre>
Le package expose aussi une <a href="https://www.rdocumentation.org/packages/RNeo4j/versions/1.6.4">API</a> permettant de manipuler la base de données (création/modification de noeuds et de relations).
<div id="enrichissement-de-la-base" class="section level2">
<h2>Enrichissement de la base</h2>
Il est possible d’enrichir le graphe existant, en effectuant une <strong><a href="https://en.wikipedia.org/wiki/Bipartite_network_projection">projection</a></strong> à partir des noeuds de type <strong>groupes</strong> et <strong>membres</strong> (labels <code>Group</code> et <code>Member</code>).

La commande suivante va créer une relation <code>HAS_COMMON_MEMBERS</code> entre les groupes, avec une propriété <code>weight</code> représentant le nombre de membres en commun :
<pre><code>MATCH (g1:Group)&lt;-[:IS_MEMBER]-(m:Member)-[:IS_MEMBER]-&gt;(g2:Group)
    WHERE g1 &lt;&gt; g2
WITH g1, g2, COUNT(m) AS w
MERGE (g1)-[:HAS_COMMON_MEMBERS {weight: w}]-(g2);</code></pre>
La requête suivante permet de comptabiliser le nombre de relations <code>HAS_COMMON_MEMBERS</code> ainsi créées :
<pre><code>MATCH ()-[r:HAS_COMMON_MEMBERS]-() RETURN COUNT(r) AS GroupCommonCount;

+------------------+
| GroupCommonCount |
+------------------+
| 9516             |
+------------------+</code></pre>
</div>
<div id="utilisation-avancee" class="section level2">
<h2>Utilisation avancée</h2>
Jusqu’ici, nous avons utilisé Neo4j pour une interrogation simple de nos données. Allons un peu plus loin, avec des opérations plus avancées comme :
<ul>
 	<li>La recommandation de groupes.</li>
 	<li>Le calcul du chemin le plus court entre deux groupes.</li>
</ul>
<div id="filtre-collaboratif" class="section level3">
<h3>Filtre collaboratif</h3>
Il s’agit de répondre à la question suivante : quels groupes seraient susceptibles d’intéresser une personne ?

Pour répondre, nous allons :
<ol>
 	<li>Partir des groupes dont la personne est membre.</li>
 	<li>Collecter les groupes des membres de ces groupes.</li>
 	<li>Proposer les groupes ayant le plus grand nombre de personnes membres de nos groupes.</li>
</ol>
Le résultat s’obtient avec la requête suivante :
<pre><code>WITH
    // Identifiant de la personne pour laquelle effectuer une recommandation
    133297112 AS Me
// 1. Groupes (g_reco) des membres (other) de mes (me) groupes (g_me)...
MATCH (me:Member {id: Me})-[:IS_MEMBER]-&gt;(g_me:Group)&lt;-[:IS_MEMBER]-(other:Member)-[:IS_MEMBER]-&gt;(g_reco:Group)
WHERE
    // ... dont je ne suis pas membre.
    NOT (me)-[:IS_MEMBER]-&gt;(g_reco)
WITH
    // Groupes dont je ne suis pas membre 
    DISTINCT g_reco AS RecommendedGroups,
    // Nombre de membres en commun avec ce groupe
    COUNT(DISTINCT other) AS CommonMemberCount
    ORDER BY CommonMemberCount DESC
// 2. Noms des groupes recommandés, avec le nombre de membres en commun
RETURN
    RecommendedGroups.name,
    CommonMemberCount
LIMIT 10;</code></pre>
La recommandation retournée (résultat limité aux 10 premiers groupes) :
<pre><code>+------------------------------------------------------------------------------+
| RecommendedGroups.name                                   | CommonMemberCount |
+------------------------------------------------------------------------------+
| "UX Rennes"                                              | 670               |
| "Le Shift"                                               | 669               |
| "Agile Rennes"                                           | 636               |
| "La Cordée Rennes - partage, événements et bonne humeur" | 634               |
| "RennesJS"                                               | 545               |
| "Docker Rennes"                                          | 534               |
| "Osons le Leadership Rennes"                             | 424               |
| "EXPAIR - Applications Connectées et Intelligentes"      | 266               |
| "Crowdfunding GwenneG Meetup"                            | 236               |
| "Rennes Growth Hacking Meetup"                           | 230               |
+------------------------------------------------------------------------------+</code></pre>
</div>
<div id="chemin-le-plus-court" class="section level3">
<h3>Chemin le plus court</h3>
Partons du principe que l’inscription dans un nouveau groupe nécessite d’être coopté par un membre de ce groupe, et que cette cooptation n’est possible que si cette personne est membre d’un de nos groupes (cette personne étant donc une relation de premier <a href="https://fr.wikipedia.org/wiki/Degré_(théorie_des_graphes)">degré</a>).

Exemple :
<ul>
 	<li>A est membre du groupe G1.</li>
 	<li>B est membre du groupe G1 et G2.</li>
 	<li>C est membre du groupe G2 et G3.</li>
</ul>
<ol>
 	<li>B peut coopter A pour qu’il devienne membre du groupe G2.</li>
 	<li>Maintenant que A est membre du groupe G2, C sera en mesure de coopter A pour qu’il devienne membre du groupe G3.</li>
</ol>
Le parcours de cooptation pour A afin de devenir membre du groupe G3 sera G1-&gt;G2-&gt;G3.

Il s’agit donc de répondre à la question suivante : en l’état actuel des relations, par combien de groupes faudra-t’il s’inscrire pour être admis dans un groupe cible ?

Le résultat s’obtient avec la requête suivante (avec ici le groupe cible “Communauté vidéo iPhone Bretagne”), qui s’appuie sur la fonction <strong><a href="https://neo4j.com/docs/developer-manual/current/cypher/clauses/match/#query-shortest-path">shortestPath</a></strong>, implémentée dans Neo4j :
<pre><code>WITH
    133297112 AS Me,
    "Communauté vidéo iPhone Bretagne" AS TargetGroupName
MATCH (me:Member {id: Me})-[:IS_MEMBER]-&gt;(g_me:Group)
MATCH path = shortestPath((g_me:Group)-[:HAS_COMMON_MEMBERS*]-(g_target:Group {name: TargetGroupName}))
RETURN me, path, length(path) AS RelCount
ORDER BY RelCount ASC
LIMIT 1;</code></pre>
<img class="aligncenter size-full wp-image-3820" src="http://data-bzh.fr/wp-content/uploads/2017/11/recommender01.png" alt="Chemin le plus court 1" width="1200" height="538" />

Cette même requête peut-être enrichie afin d’exclure certains groupes (ici le groupe “Meetup La French Tech Rennes St Malo”) de notre parcours de cooptation :
<pre><code>WITH
    133297112 AS Me,
    "Communauté vidéo iPhone Bretagne" AS TargetGroupName,
    ["Meetup La French Tech Rennes St Malo"] AS ExcludeGroupNames
MATCH (me:Member {id: Me})-[:IS_MEMBER]-&gt;(g_me:Group)
WHERE NOT g_me.name IN ExcludeGroupNames
MATCH path = shortestPath((g_me:Group)-[:HAS_COMMON_MEMBERS*..3]-(g_target:Group {name: TargetGroupName}))
RETURN me, path, length(path) AS RelCount
ORDER BY RelCount ASC
LIMIT 1;</code></pre>
<img class="aligncenter size-full wp-image-3821" src="http://data-bzh.fr/wp-content/uploads/2017/11/recommender02.png" alt="Chemin le plus court 2" width="1200" height="537" />
<h2>Conclusion</h2>
Nous avons couvert ici quelques notions propres aux bases de données graphe et à Neo4j. Mais il reste beaucoup à évoquer, et nous espérons que cet article vous aura donné envie d’approfondir le sujet.

Le code <strong>R</strong> utilisé pour la rédaction de cette série d’articles est disponible sur notre dépôt de sources <a href="https://github.com/DataBzh/territoire/tree/master/MeetupRennes">Github</a>.

</div>
</div>
</div>