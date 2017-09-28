---
ID: 320
post_title: Logiciel — Découvrez R
author: Colin FAY
post_excerpt: ""
layout: post
permalink: http://data-bzh.fr/logiciel-r/
published: true
post_date: 2016-02-28 18:00:28
---
<h2>Quand il est question de traitement de données, le panel d'outils disponibles est large. Parmi eux, R, logiciel libre d'analyse statistique et de visualisation.</h2>
<!--more-->
<h3></h3>
<h3>R, un peu d'histoire</h3>
Avec bientôt 25 ans d'existence, R a vu le jour en tant que projet GNU au début des années 90 dans les laboratoires Bell, et perdure aujourd'hui par le soutien d'une communauté passionnée de développeurs et de statisticiens regroupé au sein du <em>R Development Core Team</em>. Basé sur le langage de programmation S, ce <strong>logiciel de traitement de données</strong> a connu ces dernières années une popularité grandissante parmi les statisticiens et des data miners.

Pour télécharger R, rien de plus simple : rendez-vous sur la page dédiée du <a href="https://cran.r-project.org/" target="_blank">Comprehensive R Archive Network</a>.

&nbsp;
<h3>R, qu'est-ce que c'est ?</h3>
Environnement de traitement statistique, ce logiciel open source affiche une interface qui vous permet de <strong>charger</strong>, d'<strong>organiser</strong> et de <strong>manipuler</strong> des<strong> jeux de données</strong>. Ses points forts ? Vous pouvez traiter des <strong>volumes conséquents de données</strong>, créer des graphiques entièrement paramétrables, mais surtout installer de nombreux packages (des "options" supplémentaires) afin d'effectuer les calculs que vous souhaitez. En d'autres termes, même si la solution de départ est déjà très puissante, vous pouvez toujours y ajouter des extensions pour (entre autres) effectuer certains calculs, pour du text-mining ou encore vous pour connecter à des API — et les possibilités sont presque illimitées !

À noter, <strong>R est un langage interprété et non compilé</strong> — en d'autres termes, les commandes que vous tapez au clavier seront directement exécutées, vous n'aurez pas à construire un programme complet avant de vous lancer.

&nbsp;
<h3>R, en pratique</h3>
Lors du lancement de R, vous affichez une console, qui vous permettra d'<strong>entrer vos premières lignes de codes</strong> : par exemple, si vous y tapez "78-8", l'interface vous donnera le résultat de cette soustraction. Mais vous vous en doutez, R est bien plus puissant qu'une simple calculatrice ! En effet, ce logiciel vous permet de<strong> travailler avec des objets</strong>, qui sont des "cases mémoires". Attention, en R, tout est objet — ces derniers sont utilisés pour <strong>contenir des données</strong> ou pour <strong>effectuer des actions</strong>.

En R, tous les objets ont un <em>nom</em>, un <em>contenu</em>, mais aussi des <em>attributs</em>, qui vont décrire le type de données que l'on y trouve — les deux attributs minimum étant le <strong>mode</strong> (numérique, caractère, logique ou complexe), indiquant ce que peut contenir l'objet, et la <strong>longueur</strong>, affichant la taille des données. Beaucoup d'autres attributs peuvent venir compléter la définition.

<img class="aligncenter size-full wp-image-327" src="http://dev.data-bzh.fr/wp-content/uploads/2016/02/Applcation-statistique-R-2.jpg" alt="Interface du logiciel R" width="1000" height="430" />
<h3></h3>
<h3>R, quelques lignes basiques</h3>
En pratique, comment ça se passe ? C'est l'heure de mettre la main à la pâte ! À l'heure qu'il est, vous avez probablement déjà téléchargé et installé R. Non ? Eh bien c'est le moment. Nous allons <strong>travailler sur un jeu de données simple</strong>, la population bretonne en 2009, disponible sur <a href="https://www.data.gouv.fr/fr/datasets/population-legale-en-bretagne-2009/" target="_blank">data.gouv</a>.
<h4>Charger le csv en R</h4>
Une fois en R, nous allons d'abord charger le document csv dans l'environnement. Pour cela, voici la commande à entrer :
<p style="padding-left: 30px;"><em>pop &lt;- read.csv("emplacement\du\document\insee_pop_2009.csv")</em></p>
Qu'est-ce que cela veut dire, tout ça ? <em>pop</em> est le nom de l'objet que vous créez pour contenir vos données. L'opérateur <em>&lt;-</em> assigne à l'intérieur de l'objet tout ce qui se trouve à sa droite. <em>read.csv</em> est la commande indiquant à R qu'il faut lire un fichier csv, et le chemin entre <em>("")</em> spécifie l'endroit où R doit aller chercher votre document sur votre disque dur.
<h4>Trouver le nom des colonnes.</h4>
Avant de travailler des données, il faut savoir dans quelle colonne chercher ! Pour cela, rien de plus simple, il suffit de taper la commande :
<p style="padding-left: 30px;"><em>names(pop)</em></p>
Lorsque vous chargez votre csv en R, read.csv prend par défaut la valeur <em>header=TRUE</em>. En d'autres termes, si vous ne modifiez pas cet attribut, la première ligne de votre document sera lue comme un en-tête. La commande <em>names</em> permet d'afficher nom de colonnes.

Vous obtenez donc :
<p style="padding-left: 30px;"><em>[1] "gml_id"     "ID_DEPT"    "ID_ARROND"  "ID_CANTON"  "INSEE"      "COMMUNE"</em>
<em> [7] "MUNICIPALE" "POP_A_PART" "TOTALE"     "Surf_ha"</em></p>

<h4>Effectuer la moyenne et la médiane de ces colonnes</h4>
Chaque ligne représente une commune, et la colonne regroupant le nombre d'habitants est "TOTALE". Pour obtenir la moyenne, voici la commande à taper dans votre interface :
<p style="padding-left: 30px;"><em>mean(pop$TOTALE)</em></p>
Ici, l'opérateur <em>mean</em> fait appel à la fonction de moyenne. L'opérateur <em>$</em> vous permet de sélectionner la colonne qui vous intéresse. Pour une médiane, il vous suffit de replacer mean par.... <em>median</em>, tout simplement ! <em>sd</em> et <em>var</em>, quant à eux, affichent respectivement l'écart-type et la variance.

N'hésitez pas à faire le tour de ce jeu de données, qui pourra vous servir de point de départ pour votre exploration de ce puissant logiciel — de nombreuses manipulations peuvent être effectuées. Un peu perdu ? N'hésitez pas à consulter l'aide en ligne, disponible en tapant la commande <em>help.start().</em>

&nbsp;