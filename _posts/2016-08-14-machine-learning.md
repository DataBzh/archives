---
ID: 1252
post_title: 'Dis, c&rsquo;est quoi le machine learning ?'
author: Colin FAY
post_excerpt: ""
layout: post
permalink: http://data-bzh.fr/machine-learning/
published: true
post_date: 2016-08-14 18:03:07
---
<h2 class="p1">Parmi les thèmes à la mode dans le (petit) monde de la science des données, nous entendons partout "Machine Learning". À un tel point qu'il devient presque difficile à ceux qui ne savent pas de quoi il en retourne de demander : dis, en fait, c'est quoi le machine learning ? Alors, prenons le taureau par les cornes, et demandons-le nous une bonne fois pour toute.</h2>
<!--more-->
<p class="p1">Il est dans toutes les bouches, sous tous les crayons et de toutes les révolutions... Nous parlons bien sûr du "Machine Learning", cette expression immanquable pour qui passe un peu de temps sur le web. Mais concrètement, de quoi il en retourne ?</p>

<h3 class="p1">Machine learning, un peu d'histoire</h3>
<p class="p1">Connue sous le nom d'apprentissage automatique dans la langue de Molière (mais il faut avouer que Machine Learning sonne mieux, n'est-il pas ?), cette méthode n'est pourtant née de la dernière pluie — on peut faire remonter <strong>au milieu du 18e siècle et à Thomas Bayes</strong> les premières fondations de l'apprentissage statistique.</p>
<p class="p1">Pourquoi parle-t-on "d'apprentissage" des machines ? Si vous vous êtes tourné vers Wikipédia pour avoir une réponse, il n'est pas sûr que vous ayez trouvé votre bonheur. Pour faire simple, on parle d'apprentissage dans le sens où <strong>une machine est capable de créer un modèle pour prédire une information face à une donnée nouvelle à partir de données stockées qu'on lui fournit en entrée</strong> (en quelques sortes, comme le cerveau humain).</p>
<p class="p1">Et plus on lui en offre, i.e plus les quantités de base sont élevées, plus la machine arrive à sortir une réponse pertinente lorsqu’elle se trouve face à une donnée inédite — les mathématiciens d'il y a quelques siècles n'étant pas équipés d’outils aussi performants que ceux dont disposent les data scientists d'aujourd'hui, il est simple de comprendre pourquoi les méthodes de machine learning connaissent un essor plus fort depuis les années 2000...</p>

<h3 class="p1">Le machine learning, en clair</h3>
<p class="p1">Il existe deux grands types d'algorithmes en machine learning : <strong>supervisés</strong> ou non <strong>supervisés</strong> (oui, il en existe d'autres, mais nous ne les aborderons pas dans ce billet). On parle d'algorithmes supervisés lorsque les éléments en entrée sont déjà classifiés en catégories ou en groupes (autrement dit, il y a déjà des exemples de relations entre données) — ici, les données nouvelles sont distribuées dans les catégories qui ont été posées par avance. Les algorithmes non-supervisés, quant à eux, n'ont pas d’étiquettes prédéfinies, mais vont traiter les éléments selon leur ressemblance / proximité — les données nouvelles seront alors classées dans ces catégories de ressemblances / proximité.</p>
<p class="p1"><img class="aligncenter size-full wp-image-1348" src="http://dev.data-bzh.fr/wp-content/uploads/2016/08/regression-2.jpg" alt="Regression lineaire" width="640" height="300"></p>
<p class="p1">Schématiquement, si l'on imagine que des formes sont catégorisées en couleur (les ronds en bleu, les carrés en rouge), un algorithme supervisé se verra fournir, en amont, le classement de correspondance forme-couleur, avec la base de données. Ainsi, quand il rencontrera une forme inédite, il saura la classer dans la catégorie adéquate. Un algorithme non supervisé, au contraire, n’a pas les étiquettes par avance, et classera selon la couleur, ou la forme, sans pouvoir labelliser les forme autrement que par des groupes de proximité. Un rond inédit sera donc catégorisé en fonction de sa ressemblance plus ou moins grande avec les formes du groupes de départ — donc avec les autres ronds, et une forme rouge inédite sera de son côté classée avec les formes qui lui ressemblent le plus sur le caractère couleur : les carrés.</p>

<h3 class="p1">Le Machine learning, pour quoi faire ?</h3>
<p class="p1">Vous vous en doutez, les enjeux de l'apprentissage automatique dépassent le simple cataloguage de formes en couleur... Communément, on considère que les modèles les plus courants de ML se regroupent en trois catégories :</p>
<p class="p1">- <strong>Classification</strong> : une technique qui permet de <strong>prédire la catégorie</strong> dans laquelle ranger une nouvelle donnée, par exemple grâce à un arbre de décision.</p>
<p class="p1">- <strong>Régression</strong> : ici, il s’agit de <strong>trouver la fonction qui décrit au mieux la relation</strong> entre des variables d'un jeu de données.<span class="Apple-converted-space">&nbsp; </span>Nous vous le donnons dans le mille, la régression linéaire fait partie de cette classe.</p>
<p class="p1">- <strong>Clustering</strong> : une famille d’algorithme permettant de <strong>créer des groupes de données</strong> de façon à ce que tous les éléments d'un groupe soient semblables, et que les groupes séparés différent au maximum. Ici se trouve (entre autres) la méthode des k-moyennes.</p>
<p class="p1">En clair, vaste sujet que le machine learning, et la thématique risque de gagner en popularité au fil des années : les géants du web y voient (et à juste titre) une promesse d'avenir glorieux. Une bonne raison de passer un peu plus de temps sur le web et le nez dans les bouquins pour ... (roulements de tambour)... apprendre l'apprentissage automatique !</p>