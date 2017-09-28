---
ID: 699
post_title: >
  Premiers pas en text-mining avec R –
  Partie 3
author: Colin FAY
post_excerpt: ""
layout: post
permalink: http://data-bzh.fr/text-mining-r-part-3/
published: true
post_date: 2016-05-01 18:00:09
---
<h2 class="p1">Troisième partie de notre séquence sur le text mining avec R. Dans ce billet : créer un nuage de mots.</h2>
<!--more-->

<em>Note — Ce billet fait partie d'une série de billets sur le text-mining avec R. Nous vous invitons à les consulter dans l'ordre :</em>
<em>- <a href="http://data-bzh.fr/text-mining-r-part-1/" target="_blank" rel="noopener noreferrer">Premiers pas en text-mining avec R – Partie 1</a></em>
<em>- <a href="http://data-bzh.fr/text-mining-r-part-2/" target="_blank" rel="noopener noreferrer">Premiers pas en text-mining avec R – Partie 2</a></em>
<em>- <a href="http://data-bzh.fr/text-mining-r-part-3/" target="_blank" rel="noopener noreferrer">Premiers pas en text-mining avec R – Partie 3
</a>- <a href="http://data-bzh.fr/text-mining-r-part-4/" target="_blank" rel="noopener noreferrer">Premiers pas en text-mining avec R - Partie 4</a></em>
<p class="p1"><span style="font-size: 1.125rem;">Un nuage de mots, pour quoi faire ?</span></p>
<p class="p1">Également appelé "Wordcloud", un nuage de mots permet de représenter visuellement les mots les plus récurrents dans un corpus. Comment ? Leur <strong>fréquence est proportionnelle à leur taille dans le nuage</strong> : concrètement, plus un mot est présent dans le texte analysé, plus sa place dans le nuage est importante. Des couleurs différentes sont également utilisées pour identifier les entrées du corpus.</p>
<p class="p1">Le point fort de cette visualisation : elle est facilement comprise par l’œil humain, qui saisit en quelques secondes les termes centraux.</p>
[Tweet "#TextMining — #Dataviz et nuage de mots avec #RStats"]
<h3 class="p1">Nettoyer le corpus</h3>
<p class="p1">Afin d’obtenir un nuage de mots de qualité, il est <strong>indispensable de se séparer des mots peu abondants</strong> — en effet, un corpus comme celui que nous analysons dans cette suite de billets compte 39 114 mots dans sa version filtrée... Pourtant, sur tous ces mots, seulement 741 entrées sont citées plus de 100 fois...</p>
<p class="p1">Autant de mots peu abondants, utiles pour d’autres analyses, mais qui viendront ici <strong>nuire à la lisibilité globale du nuage</strong>. Qui plus est, pour éviter à votre laptop de tourner à plein régime lors de la construction d’un nuage de plus de 12 000 entrées, n’ayez pas peur de vous séparer des mots superflus !</p>

<h3 class="p1">Obtenir un nuage de mots avec R</h3>
<h4 class="p1">Créer le nuage de mots :</h4>
<p class="p1">Lors de la création du nuage de mot, R vous permet de <strong>nettoyer directement votre corpus</strong> en assignant une valeur à deux arguments de wordcloud() :
– min.freq = x : les mots avec une fréquence inférieure à x ne seront pas représentés dans le nuage
– max.words = y : le nuage ne comptera pas plus de y mots</p>
<p class="p1">Lequel choisir ? La réponse dépend des situations d’analyse. Pour le premier, vous devrez avoir une idée des fréquences moyennes de votre corpus, là où la seconde vous permet de sélectionner un nombre de ligne, indépendamment de votre connaissance effective des fréquences.</p>

<h4 class="p1">Le code :</h4>
<p class="p1">Pour les nuages de mots, vous aurez besoin du package wordcloud.</p>

<pre id="rstudio_console_output" class="GGHFMYIBMOB" tabindex="0"><span class="GGHFMYIBCOB ace_keyword">library("wordcloud")
library("tidyverse")
library("proustr")
library("tidytext")
</span><span class="GGHFMYIBCOB ace_keyword">books_tidy &lt;- proust_books() %&gt;%
</span> <span class="GGHFMYIBCOB ace_keyword">  mutate(text = stringr::str_replace_all(.$text, "’", " ")) %&gt;% 
</span> <span class="GGHFMYIBCOB ace_keyword">  unnest_tokens(word, text) %&gt;%
</span> <span class="GGHFMYIBCOB ace_keyword">  filter(!word %in% stopwords_iso$fr) %&gt;%
</span> <span class="GGHFMYIBCOB ace_keyword">  count(word, sort = TRUE)
</span><span class="GGHFMYIBCOB ace_keyword">wordcloud(books_tidy$word, books_tidy$n, max.words=100, rot.per=FALSE, colors= c("#973232", "#1E5B5B", "#6D8D2F", "#287928"))</span></pre>
<a href="http://data-bzh.fr/wp-content/uploads/2016/05/wordcloud_r_tidy_tm.png"><img class="aligncenter size-full wp-image-3557" src="http://data-bzh.fr/wp-content/uploads/2016/05/wordcloud_r_tidy_tm.png" alt="" width="800" height="800" /></a>
<h4 class="p1">Racinisation pour le nuage ?</h4>
<p class="p1">Nous avions vu dans le second billet comment effectuer une racinisation sur un corpus avec R. Comme nous le notions alors, cette méthode permet de tronquer les préfixes et suffixes des mots afin de les regrouper autour de leur racine, pour un gain de 50 % sur la base globale. Cependant, à des fins de visualisation, ce <strong>processus donne un résultat moins lisible</strong>, les racines n’étant pas des mots "réels".</p>

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