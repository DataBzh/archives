---
ID: 440
post_title: >
  Premiers pas en text-mining avec R –
  Partie 2
author: Colin FAY
post_excerpt: ""
layout: post
permalink: http://data-bzh.fr/text-mining-r-part-2/
published: true
post_date: 2016-04-03 18:00:35
---
<h2>Seconde partie de notre série sur le text-mining avec R. Dans ce volet : nettoyer un corpus par racinisation.</h2>
<!--more-->

<em>Note — Ce billet fait partie d'une série de billets sur le text-mining avec R. Nous vous invitons à les consulter dans l'ordre :</em>
<em>- <a href="http://data-bzh.fr/text-mining-r-part-1/" target="_blank" rel="noopener noreferrer">Premiers pas en text-mining avec R – Partie 1</a></em>
<em>- <a href="http://data-bzh.fr/text-mining-r-part-2/" target="_blank" rel="noopener noreferrer">Premiers pas en text-mining avec R – Partie 2</a></em>
<em>- <a href="http://data-bzh.fr/text-mining-r-part-3/" target="_blank" rel="noopener noreferrer">Premiers pas en text-mining avec R – Partie 3
</a>- <a href="http://data-bzh.fr/text-mining-r-part-4/" target="_blank" rel="noopener noreferrer">Premiers pas en text-mining avec R - Partie 4</a></em>

<span style="font-size: 1.125rem;">La lemmatisation</span>

Dans une langue, un mot peut prendre plusieurs formes : singulier ou pluriel, féminin ou masculin, conjugaison pour les verbes, etc. Toutes ces déclinaisons ont pour base une <strong>unité lexicale unique et autonome</strong>, que la linguistique nomme <strong>lemme</strong>. Ainsi, un lemme correspond à <strong>la plus petite unité lexicale faisant sens</strong>, qui est souvent l'équivalent de la plus petite unité pouvant constituer une entrée dans le dictionnaire.

Technique liée au text-mining, la lemmatisation d'un un corpus consiste à regrouper les déclinaisons d'un lemme au sein de<strong> la même entrée dans votre base de données</strong>. En d'autres termes, le processus de lemmatisation fait correspondre <em>nettoyait</em> et <em>nettoyant</em> au sein d'une même unité : <em>nettoyer</em>. Ce type de manipulation vous permet de gagner en pertinence : vous n'analyserez pas ces deux mots comme deux unités distinctes, mais comme une seule unité.

[Tweet "#DataScience — #TextMining : lemmatisation et racinisation avec #RStats"]
<h3>Lemmatisation ou racinisation ?</h3>
À l'inverse d'un lemme, la racine d'un mot n'est pas unité qui fait sens par elle même, ce n'est pas un mot réel. En effet, la <strong>racine est dépouillée de ses préfixes et suffixes</strong>, ainsi que de toutes ses déclinaisons, la rendant inutilisable en tant que telle. Également liée au text-mining, la racinisation consiste donc à nettoyer son corpus en regroupant l'ensemble des déclinaisons autour d'une même racine.
<h4>Choisir entre ces deux techniques ?</h4>
Chacun de ces processus de nettoyage  présente ses avantages et ses inconvénients. Le point fort de la racinisation étant la <strong>simplicité de mise en place</strong> — la lemmatisation demande un dictionnaire complexe liant les différentes formes d'un mot (par exemple, <em>suis est </em>et<em> sommes</em> sont liés au sein de la même entrée <em>être</em>), là où la racinisation est moins complexe, utilisant une <strong>série</strong> prédéfinie de <strong>préfixes et suffixes</strong> qui sont tronqués sur les mots du corpus (mais qui, potentiellement, ne fera pas correspondre <em>suis</em> et <em>est</em>).

Ainsi, dans le cadre de notre série sur l'introduction au text-mining avec R, nous nous contenterons d'aborder la technique la plus facile d'accès, celle de racinisation, ou <em>stemming</em> dans la langue de Shakespeare.
<h3>Racinisation avec R : quelques lignes de code</h3>
Souvenez-vous de notre <a href="http://data-bzh.fr/text-mining-r-part-1/">première partie sur le text-mining</a>. Le stemming intervient durant la<strong> seconde étape, celle de nettoyage de corpus</strong> — <em>toutes les commandes à la suite interviennent après la dernière ligne de commande de l'étape 2 de notre premier volet sur le text-mining</em>.
<h4>Le code :</h4>
Racinisation
<pre id="rstudio_console_output" class="GGHFMYIBMOB" tabindex="0">wordStem(books_tidy$word, language = "french")
# La liste des langages supportés est disponible avec 
# la fonction getStemLanguages()</pre>
<h4>Quel bénéfice pour le text-mining ?</h4>
Afin d'estimer le gain d'une racinisation, analysons la taille des deux corpus, l'un avant processus de tri, le second après. Malheureusement, le stemming ne fonctionnant
<pre id="rstudio_console_output" class="GGHFMYIBMOB" tabindex="0"><span class="GGHFMYIBCOB ace_keyword">library("SnowballC")
library("tidyverse")
library("proustr")
library("tidytext")
</span><span class="GGHFMYIBCOB ace_keyword">books_tidy &lt;- proust_books() %&gt;%
</span> <span class="GGHFMYIBCOB ace_keyword">  mutate(text = stringr::str_replace_all(.$text, "’", " ")) %&gt;% 
</span> <span class="GGHFMYIBCOB ace_keyword">  unnest_tokens(word, text) %&gt;%
</span> <span class="GGHFMYIBCOB ace_keyword">  count(word, sort = TRUE)
</span><span class="GGHFMYIBCOB ace_keyword">nrow(books_tidy)
</span>[1] 39672</pre>
<code></code>
<pre id="rstudio_console_output" class="GGHFMYIBMOB" tabindex="0"><span class="GGHFMYIBCOB ace_keyword">stem &lt;- wordStem(books_tidy$word, language = "french")
</span><span class="GGHFMYIBCOB ace_keyword">length(unique(stem))
</span>[1] 16917</pre>
Ainsi, lorsque l'on compare les deux data.frame, nous constatons une <strong>diminution de plus de moitié de la taille de notre corpus</strong> — ce qui nous permet de réduire la marge de bruit en appliquant cette première étape de nettoyage de texte.
<h4>Code complet</h4>
<a href="https://github.com/DataBzh/blog/blob/master/text-mining.R" target="_blank" rel="noopener noreferrer"><strong>Retrouvez le code complet sur notre Github</strong></a>
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