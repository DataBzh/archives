---
ID: 3678
post_title: 'Premiers pas en text-mining avec R &#8211; Partie 5'
author: Colin FAY
post_excerpt: ""
layout: post
permalink: >
  http://data-bzh.fr/premiers-pas-en-text-mining-avec-r-partie-5/
published: true
post_date: 2017-09-05 14:00:59
---
<h2>5e volet de notre série sur le text-mining avec R. Aujourd'hui, les expressions régulières.</h2>
<!--more-->

<em>Note — Ce billet fait partie d'une série de billets sur le text-mining avec R. Nous vous invitons à les consulter dans l'ordre :</em>
<em> - <a href="http://data-bzh.fr/text-mining-r-part-1/" target="_blank" rel="noopener noreferrer">Premiers pas en text-mining avec R – Partie 1</a></em>
<em> - <a href="http://data-bzh.fr/text-mining-r-part-2/" target="_blank" rel="noopener noreferrer">Premiers pas en text-mining avec R – Partie 2</a></em>
<em> - <a href="http://data-bzh.fr/text-mining-r-part-3/" target="_blank" rel="noopener noreferrer">Premiers pas en text-mining avec R – Partie 3
</a>- <a href="http://data-bzh.fr/text-mining-r-part-4/" target="_blank" rel="noopener noreferrer">Premiers pas en text-mining avec R - Partie 4</a></em>
<h4>Code complet</h4>
<a href="https://github.com/DataBzh/blog/blob/master/text-mining.R" target="_blank" rel="noopener noreferrer"><strong>Retrouvez le code complet sur notre Github</strong></a>
<h3>Expressions régulières : késako ?</h3>
Posons les bases : qu'est-ce qu'une expression régulière ? <strong>Egalement appelée regex (pour regular expression), l'expression régulière est un motif syntaxique destiné à décrire de manière logique une unité de langage</strong>... autrement dit un ensemble régulier : un mot, une lettre, un chiffre, une répétition, etc.

L'utilité ? <strong>Pouvoir rechercher, manipuler et contrôler des chaines de caractères</strong>. Les expressions régulières sont par exemple utilisées lorsque vous vous inscrivez sur un site internet avec votre mail : le site internet vérifie que vous mail répond bien à l'expression régulière "mot@mot.mot". Dans la pratique, un mail est bien plus complexe que cette simple suite, mais vous comprenez l'idée. La même chose s'applique pour les dates, les numéros de téléphone, les codes postaux, et (presque) tout ce qui est imaginable...
<h3>Regex et text-mining</h3>
Bon, c'est bien beau tout ça, mais quelle utilité pour le text-mining ? Une fois les expressions régulières maîtrisées, <strong>vous mettez dans votre besace un puissant outil de text-mining.</strong> Surtout que les regex sont pour la plupart agnostiques, c'est-à-dire indépendantes du langage de programmation. Vous souhaitez repérer toutes les occurrences de "un mot suivi de plus d'un point d'exclamation" ? Direction une regex. "Tous les mots de deux lettres" ? Direction une regex. Et ainsi de suite.
<h3>R et regex</h3>
Retour à notre langage de prédilection : R. Ce dernier vient avec deux librairies standards : les  "extended regular expressions", et les "Perl-like", venant du langage du même nom.

<strong>R {base} repose sur le standard <a href="https://www.regextester.com/eregsyntax.html">POSIX 1003.2</a></strong>, décrivant les éléments sous deux formes :

- Entre crochets [:xxx:], avec :
<pre>– [:alnum:] : tous les caractères alphanumériques.
– [:alpha:] : les caractères alphabétiques uniquement, en majuscule et en minuscule.
– [:blank:] : des caractères « blancs », types espace ou tabulation
– [:cntrl:] : un caractère de contrôle
– [:digit:] : un chiffre de 0 à 9
– [:graph:] : un caractère graphique, c’est-à-dire alphanumérique ou de ponctuation.
– [:lower:] : un caractère en minuscule
– [:print:] : un caractère imprimable
– [:punct:] : une ponctuation : ! » # $ % &amp; ‘ ( ) * + , – . / : ; &lt; = &gt; ? @ [ \ ] ^ _ ` { | } ~.
– [:space:] : un espace (tabulation, nouvelle ligne, retour chariot…)
– [:upper:] : un caractère en majuscule
– [:xdigit:] : un caractère du système hexadécimal : 0 1 2 3 4 5 6 7 8 9 A B C D E F a b c d e f.</pre>
- En éléments de ponctuation, avec :
<pre>. : renvoie à n’importe quel caractère
^ : le caractère suivant est au début d’une chaine
$ : le caractère suivant est en fin de chaine
– ? : le caractère précédent est optionnel, et ne devra être trouvé qu’une seule fois
– * : le caractère sera trouvé zéro fois ou plus
– + : le caractère sera trouvé une fois ou plus
– {n} : le caractère sera trouvé n fois
– {n,} : le caractère sera trouvé au moins n fois
{n,m} : le caractère sera trouvé entre n et m fois.</pre>
<p style="text-align: right;"><a href="https://thinkr.fr/r-les-expressions-regulieres/">(listes empruntées à ThinkR)</a></p>
À noter que pour faire référence à ces éléments de manière littérale, il vous faudra les échapper en les précédant de \ — qui doit lui aussi être échappé. En clair, pour faire référence à un point, on utilisera " \\. ".
<h3>R et les regex, par l'exemple</h3>
Et donc, en pratique, on fait comment ? Vous pouvez, par exemple, utiliser la fonction <code>str_extract_all()</code>, du package {stringr}. Testons la sur un extrait aléatoirement tiré de Proust.
<pre id="rstudio_console_output" class="GNKRCKGCFSB" tabindex="0">library(proustr)
library(stringr)
library(dplyr)
proust &lt;- proust_books()
txt &lt;- sample_n(proust, 1) %&gt;% 
 select(text) %&gt;%
 unlist

txt
"Comme nous y rencontrions parfois M. Vinteuil, très sévère pour 
« le genre déplorable des jeunes gens négligés, dans les idées de 
l’époque actuelle », ma mère prenait garde que rien ne clochât dans
ma tenue, puis on partait pour l’église. C’est au mois de Marie que
je me souviens d’avoir commencé à aimer les aubépines. N’étant pas 
seulement dans l’église, si sainte, mais où nous avions le droit 
d’entrer, posées sur l’autel même, inséparables des mystères à la 
célébration desquels elles prenaient part, elles faisaient courir 
au milieu des flambeaux et des vases sacrés leurs branches attachées 
horizontalement les unes aux autres en un apprêt de fête, et 
qu’enjolivaient encore les festons de leur feuillage sur lequel étaient 
semés à profusion, comme sur une traîne de mariée, de petits bouquets de 
boutons d’une blancheur éclatante. Mais, sans oser les regarder qu’à 
la dérobée, je sentais que ces apprêts pompeux étaient vivants et que
c’était la nature elle-même qui, en creusant ces découpures dans les 
feuilles, en ajoutant l’ornement suprême de ces blancs boutons, avait
rendu cette décoration digne de ce qui était à la fois une réjouissance
populaire et une solennité mystique. Plus haut s’ouvraient leurs 
corolles çà et là avec une grâce insouciante, retenant si négligemment
comme un dernier et vaporeux atour le bouquet d’étamines, fines comme 
des fils de la Vierge, qui les embrumait tout entières, qu’en suivant,
qu’en essayant de mimer au fond de moi le geste de leur efflorescence,
je l’imaginais comme si ç’avait été le mouvement de tête étourdi et rapide, 
au regard coquet, aux pupilles diminuées, d’une blanche jeune fille, 
distraite et vive. M. Vinteuil était venu avec sa fille se placer à 
côté de nous. D’une bonne famille, il avait été le professeur de piano 
des sœurs de ma grand’mère et quand, après la mort de sa femme et un 
héritage qu’il avait fait, il s’était retiré auprès de Combray, on le 
recevait souvent à la maison. Mais d’une pudibonderie excessive, il cessa 
de venir pour ne pas rencontrer Swann qui avait fait ce qu’il appelait « un 
mariage déplacé, dans le goût du jour ». Ma mère, ayant appris qu’il composait, 
lui avait dit par amabilité que, quand elle irait le voir, il faudrait qu’il lui 
fît entendre quelque chose de lui. M. Vinteuil en aurait eu beaucoup de joie, 
mais il poussait la politesse et la bonté jusqu’à de tels scrupules que, se 
mettant toujours à la place des autres, il craignait de les ennuyer et de 
leur paraître égoïste s’il suivait ou seulement laissait deviner son désir. 
Le jour où mes parents étaient allés chez lui en visite, je les avais 
accompagnés, mais ils m’avaient permis de rester dehors, et comme la maison 
de M. Vinteuil, Montjouvain, était en contre-bas d’un monticule buissonneux, 
où je m’étais caché, je m’étais trouvé de plain-pied avec le salon du second 
étage, à cinquante centimètres de la fenêtre. Quand on était venu lui annoncer 
mes parents, j’avais vu M. Vinteuil se hâter de mettre en évidence sur le 
piano un morceau de musique. Mais une fois mes parents entrés, il l’avait 
retiré et mis dans un coin. Sans doute avait-il craint de leur laisser 
supposer qu’il n’était heureux de les voir que pour leur jouer de ses 
compositions. Et chaque fois que ma mère était revenue à la charge au 
cours de la visite, il avait répété plusieurs fois : « Mais je ne sais 
qui a mis cela sur le piano, ce n’est pas sa place », et avait détourné 
la conversation sur d’autres sujets, justement parce que ceux-là l’intéressaient 
moins. Sa seule passion était pour sa fille, et celle-ci, qui avait l’air 
d’un garçon, paraissait si robuste qu’on ne pouvait s’empêcher de sourire 
en voyant les précautions que son père prenait pour elle, ayant toujours des 
châles supplémentaires à lui jeter sur les épaules. Ma grand’mère faisait 
remarquer quelle expression douce, délicate, presque timide passait souvent
dans les regards de cette enfant si rude, dont le visage était semé de taches
de son. Quand elle venait de prononcer une parole, elle l’entendait avec 
l’esprit de ceux à qui elle l’avait dite, s’alarmant des malentendus possibles
et on voyait s’éclairer, se découper comme par transparence, sous la figure
hommasse du « bon diable », les traits plus fins d’une jeune fille éplorée."
# Tous les Monsieur quelque chose 
# Ici, le pattern est M, un point (échappé avec \\), un espace, et un ou plusieurs 
str_extract_all(txt, pattern = "M. [:alpha:]*")
[1] "M. Vinteuil" "M. Vinteuil" "M. Vinteuil" "M. Vinteuil" "M. Vinteuil"

# Tous les mots de cinq lettres
# Un espace, cinq caractères, un espace
str_extract_all(txt, pattern = " [:alpha:]{5} ")
 [1] " genre " " idées " " garde " " Marie " " aimer " " droit " " elles " " elles "
 [9] " vases " " leurs " " semés " " comme " " avait " " cette " " digne " " était "
[17] " leurs " " grâce " " comme " " atour " " fines " " mimer " " geste " " comme "
[25] " jeune " " était " " fille " " bonne " " avait " " piano " " sœurs " " après "
[33] " femme " " avait " " cessa " " venir " " Swann " " avait " " ayant " " avait "
[41] " quand " " irait " " chose " " bonté " " place " " allés " " avais " " comme "
[49] " était " " salon " " Quand " " était " " hâter " " piano " " doute " " jouer "
[57] " était " " cours " " avait " " avait " " parce " " seule " " était " " avait "
[65] " ayant " " jeter " " cette " " était " " Quand " " comme " " jeune "

# Tous les mots avant une virgule
str_extract_all(txt, pattern = "[:alpha:]+,")
 [1] "Vinteuil," "négligés," "tenue," "église," "sainte," 
 [6] "entrer," "même," "part," "fête," "profusion," 
[11] "mariée," "Mais," "dérobée," "qui," "feuilles," 
[16] "boutons," "insouciante," "étamines," "Vierge," "entières," 
[21] "suivant," "efflorescence," "rapide," "coquet," "diminuées," 
[26] "fille," "famille," "quand," "fait," "Combray," 
[31] "excessive," "déplacé," "mère," "composait," "que," 
[36] "voir," "joie," "que," "autres," "visite," 
[41] "accompagnés," "dehors," "Vinteuil," "Montjouvain," "buissonneux," 
[46] "caché," "étage," "parents," "entrés," "visite," 
[51] "piano," "sujets," "fille," "ci," "garçon," 
[56] "elle," "douce," "délicate," "rude," "parole," 
[61] "dite," "éclairer," "transparence,"</pre>
Simple, n'est-ce pas ? À première vue, oui. Mais dans la pratique, trouver la bonne regex est parfois un véritable casse tête. Alors, à l'entrainement !
<h3>En lire plus :</h3>
<a href="https://www.amazon.fr/gp/product/1491981652/ref=as_li_tl?ie=UTF8&amp;camp=1642&amp;creative=6746&amp;creativeASIN=1491981652&amp;linkCode=as2&amp;tag=dabz-21" rel="nofollow">Text Mining With R: A Tidy Approach</a><img style="border: none !important; margin: 0px !important;" src="http://ir-fr.amazon-adsystem.com/e/ir?t=dabz-21&amp;l=as2&amp;o=8&amp;a=1491981652" alt="" width="1" height="1" border="0" />
<a href="https://www.amazon.fr/gp/product/148336934X/ref=as_li_tl?ie=UTF8&amp;camp=1642&amp;creative=6746&amp;creativeASIN=148336934X&amp;linkCode=as2&amp;tag=dabz-21" rel="nofollow">Text Mining: A Guidebook for the Social Sciences</a><img style="border: none !important; margin: 0px !important;" src="http://ir-fr.amazon-adsystem.com/e/ir?t=dabz-21&amp;l=as2&amp;o=8&amp;a=148336934X" alt="" width="1" height="1" border="0" />
<a href="https://www.amazon.fr/gp/product/1461432227/ref=as_li_tl?ie=UTF8&amp;camp=1642&amp;creative=6746&amp;creativeASIN=1461432227&amp;linkCode=as2&amp;tag=dabz-21" rel="nofollow">Mining Text Data</a><img style="border: none !important; margin: 0px !important;" src="http://ir-fr.amazon-adsystem.com/e/ir?t=dabz-21&amp;l=as2&amp;o=8&amp;a=1461432227" alt="" width="1" height="1" border="0" />
<a href="https://www.amazon.fr/gp/product/3330006455/ref=as_li_tl?ie=UTF8&amp;camp=1642&amp;creative=6746&amp;creativeASIN=3330006455&amp;linkCode=as2&amp;tag=dabz-21" rel="nofollow">Text Mining</a><img style="border: none !important; margin: 0px !important;" src="http://ir-fr.amazon-adsystem.com/e/ir?t=dabz-21&amp;l=as2&amp;o=8&amp;a=3330006455" alt="" width="1" height="1" border="0" />
<a href="https://www.amazon.fr/gp/product/178355181X/ref=as_li_tl?ie=UTF8&amp;camp=1642&amp;creative=6746&amp;creativeASIN=178355181X&amp;linkCode=as2&amp;tag=dabz-21" rel="nofollow">Mastering Text Mining with R</a><img style="border: none !important; margin: 0px !important;" src="http://ir-fr.amazon-adsystem.com/e/ir?t=dabz-21&amp;l=as2&amp;o=8&amp;a=178355181X" alt="" width="1" height="1" border="0" />
<a href="https://www.amazon.fr/gp/product/1119282012/ref=as_li_tl?ie=UTF8&amp;camp=1642&amp;creative=6746&amp;creativeASIN=1119282012&amp;linkCode=as2&amp;tag=dabz-21" rel="nofollow">Text Mining in Practice With R</a><img style="border: none !important; margin: 0px !important;" src="http://ir-fr.amazon-adsystem.com/e/ir?t=dabz-21&amp;l=as2&amp;o=8&amp;a=1119282012" alt="" width="1" height="1" border="0" />
<a href="https://www.amazon.fr/gp/product/B00RZK7UCE/ref=as_li_tl?ie=UTF8&amp;camp=1642&amp;creative=6746&amp;creativeASIN=B00RZK7UCE&amp;linkCode=as2&amp;tag=dabz-21" rel="nofollow">Text Mining: From Ontology Learning to Automated Text Processing Applications</a><img style="border: none !important; margin: 0px !important;" src="http://ir-fr.amazon-adsystem.com/e/ir?t=dabz-21&amp;l=as2&amp;o=8&amp;a=B00RZK7UCE" alt="" width="1" height="1" border="0" />
<a href="https://www.amazon.fr/gp/product/B008KZULQ0/ref=as_li_tl?ie=UTF8&amp;camp=1642&amp;creative=6746&amp;creativeASIN=B008KZULQ0&amp;linkCode=as2&amp;tag=dabz-21" rel="nofollow">Text Mining: Classification, Clustering, and Applications</a><img style="border: none !important; margin: 0px !important;" src="http://ir-fr.amazon-adsystem.com/e/ir?t=dabz-21&amp;l=as2&amp;o=8&amp;a=B008KZULQ0" alt="" width="1" height="1" border="0" />
<a href="https://www.amazon.fr/gp/product/1627058982/ref=as_li_tl?ie=UTF8&amp;camp=1642&amp;creative=6746&amp;creativeASIN=1627058982&amp;linkCode=as2&amp;tag=dabz-21" rel="nofollow">Phrase Mining from Massive Text and Its Applications</a><img style="border: none !important; margin: 0px !important;" src="http://ir-fr.amazon-adsystem.com/e/ir?t=dabz-21&amp;l=as2&amp;o=8&amp;a=1627058982" alt="" width="1" height="1" border="0" />
<a href="https://www.amazon.fr/gp/product/B005UQLIA0/ref=as_li_tl?ie=UTF8&amp;camp=1642&amp;creative=6746&amp;creativeASIN=B005UQLIA0&amp;linkCode=as2&amp;tag=dabz-21" rel="nofollow">Text Mining: Applications and Theory</a><img style="border: none !important; margin: 0px !important;" src="http://ir-fr.amazon-adsystem.com/e/ir?t=dabz-21&amp;l=as2&amp;o=8&amp;a=B005UQLIA0" alt="" width="1" height="1" border="0" />