---
ID: 192
post_title: 'Un algorithme, qu&rsquo;est-ce que c&rsquo;est ?'
author: Colin FAY
post_excerpt: ""
layout: post
permalink: http://data-bzh.fr/algorithme/
published: true
post_date: 2016-02-14 18:00:07
---
<h2>Aujourd'hui, les algorithmes sont partout : dans nos fils d'actualités, dans nos résultats de recherche, dans nos suggestions d'achat, mais aussi dans des objets concrets comme les véhicules autonomes ou encore nos thermostats connectés. Mais alors, qu'est-ce que c'est ?</h2>
<!--more-->
<h3>L'algorithme, une définition</h3>
Un algorithme est une <strong>suite d'instructions non équivoques, données dans un ordre précis, qui permettent de résoudre un problème</strong>. Eh oui, c'est aussi simple que ça — une recette de cuisine, ou encore une liste d'indications pour se rendre à un lieu sont des algorithmes. Sur un ordinateur, il en va de même : un algorithme informatique est une suite d'instructions qui guide un ordinateur vers l'exécution d'une tâche, en vue d'un but prédéfini — résoudre un problème, ou encore traiter une série d'entrées pour obtenir un résultat.

Bien qu'aujourd'hui massivement utilisés et compris dans le domaine de l'informatique, du code et du web, les algorithmes sont pourtant omniprésents. Par exemple, vous utilisez un algorithme (une suite d'instructions) pour préparer des crêpes (votre <strong>problème</strong>) :
<ul>
	<li>Mettre la farine dans un saladier</li>
	<li>Ajouter vos œufs, l'huile et le beurre</li>
	<li>Mélanger le lait</li>
	<li>Laisser reposer</li>
	<li>Cuire à la poêle</li>
</ul>
Dans cette préparation de crêpes, les ingrédients sont vos données en entrée, les crêpes votre résultat. Et l'<strong>ordre </strong>est indispensable à la résolution du problème : vous n'obtiendrez pas de bonnes crêpes en mettant la farine à la poêle pour ensuite lui ajouter du lait.

Et la <strong>non-ambiguïté</strong>, dans tout ça ? Vous avez raison de poser la question : les instructions ci-dessus peuvent être ambiguës (qu'est-ce que de la farine ? Combien d’œufs faut-il ? Mélanger, ça veut dire quoi ?). Ainsi, dans une suite algorithmique, le niveau de précision des instructions dépend-il du niveau d'informations présentes dans son environnement. Pour reprendre l'exemple des recettes de cuisine, une liste d'ingrédient est fournie en amont de la liste d'instruction, permettant ainsi de donner à l'opérateur le contexte suffisant à la bonne exécution de la recette.

Pourquoi utiliser l'ordinateur pour effectuer des algorithmes ? Parce que ce sont des machines capables d'<strong>exécuter des suites d'instructions beaucoup plus rapidement</strong>, et pendant beaucoup plus de temps qu'un être humain. Mais alors, sur quoi reposent ces listes d'instructions ?
<h3>AND, OR et NOT vs IF, THEN et ELSE : algorithmes et booléens</h3>
Ainsi donc, nous avons une situation de départ avec des données en <strong>entrée</strong>, puis une suite d'instructions, utilisées pour obtenir un <strong>résultat</strong>. Entre les deux, deux formes d'instructions — les premières analysant la situation et donnant des instructions en fonction du caractère vrai ou faux des conditions préétablies, les secondes donnant des règles de combinaisons entre les éléments.
<h4>If (x), then (y) et else (z) : les conditions</h4>
If, then et else sont les booléens (variable à deux états, typiquement vrai ou faux) qui permettent de guider l'algorithme depuis une entrée, vers l'exécution un résultat.
<ul>
	<li>If : si la condition x est vraie</li>
	<li>Then : il exécutera l'action y</li>
	<li>Else : sinon, il exécutera l'action z</li>
</ul>
<h4>And, or et not : les combinaisons</h4>
And, or et not permettent de donner les règles de combinaison des différents éléments :
<ul>
	<li>And : conjonction des éléments</li>
	<li>Or : disjonction des éléments</li>
	<li>Not : négation d'un élément</li>
</ul>
Pour reprendre l'exemple de nos crêpes, voici comment se décrit la recette :
<ol>
	<li>IF (Farine AND Œufs AND Huile AND Beurre AND Sucre) THEN (Sortir le saladier) ELSE (Aller acheter les ingrédients OR se résigner à ne pas manger de crêpes)</li>
	<li>IF (Le saladier est sorti) THEN (Mettre la farine NOT le lait) ELSE (pas de crêpes aujourd'hui)</li>
	<li>... et ainsi de suite !</li>
</ol>
&nbsp;
<h3>Mais en quoi ça nous intéresse, tout ça ?</h3>
Dans les faits, <strong>tout traitement de données passe par un algorithme</strong>, plus ou moins complexe. Prenons par exemple un corpus d'individus, que nous voudrions trier en fonction de leur langue (cela devrait vous <a href="http://data-bzh.fr/rennes-janvier-2016/">rappeler quelque chose</a>). Pour pouvoir nous aider visuellement, nous classerons ces individus en deux colonnes : la verte et la rouge. La réalité du traitement de données est bien plus complexe, mais nous schématisons afin de nous faire comprendre :
<ul>
	<li>Tous les individus parlant français en vert, sinon en rouge :
IF (Fr) THEN (Vert) ELSE (Rouge)</li>
	<li>Tous les individus ne parlant pas français en vert :
IF (NOT Fr) THEN (Vert) ELSE (Rouge)</li>
	<li>Tous les individus parlant français ou anglais en vert :
IF (Fr OR Eng) THEN (Vert) ELSE (Rouge)</li>
	<li>Tous les individus parlant français et anglais en vert :
IF (Fr AND Eng) THEN (Vert) ELSE (Rouge)</li>
	<li>Supprimer tous les individus en rouge :
IF (Rouge) THEN (supprimer) ELSE (Garder)</li>
</ul>
La liste des combinaisons est longue, voire quasi infinie, tout comme l'est celle des possibilités de traitement d'une base de données. À vous de mettre la main à la pâte !

&nbsp;
<h3>Lecture complémentaire :</h3>
<ul>
	<li><a href="https://openclassrooms.com/courses/algorithmique-pour-l-apprenti-programmeur" target="_blank">Algorithmique pour l'apprenti programmeur</a></li>
</ul>
&nbsp;