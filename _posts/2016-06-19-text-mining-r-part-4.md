---
ID: 1099
post_title: 'Premiers pas en text-mining avec R &#8211; Partie 4'
author: Colin FAY
post_excerpt: ""
layout: post
permalink: http://data-bzh.fr/text-mining-r-part-4/
published: true
post_date: 2016-06-19 18:00:09
---
<h2>4e volet de notre série sur le text-mining avec R. Dans ce billet, visualisation des termes fréquemment associés.</h2>
<!--more-->

<em>Note — Ce billet fait partie d'une série de billets sur le text-mining avec R. Nous vous invitons à les consulter dans l'ordre :</em>
<em> - <a href="http://data-bzh.fr/text-mining-r-part-1/" target="_blank" rel="noopener noreferrer">Premiers pas en text-mining avec R – Partie 1</a></em>
<em> - <a href="http://data-bzh.fr/text-mining-r-part-2/" target="_blank" rel="noopener noreferrer">Premiers pas en text-mining avec R – Partie 2</a></em>
<em> - <a href="http://data-bzh.fr/text-mining-r-part-3/" target="_blank" rel="noopener noreferrer">Premiers pas en text-mining avec R – Partie 3
</a>- <a href="http://data-bzh.fr/text-mining-r-part-4/" target="_blank" rel="noopener noreferrer">Premiers pas en text-mining avec R - Partie 4</a></em>
<h4>Code complet</h4>
<a href="https://github.com/DataBzh/blog/blob/master/text-mining.R" target="_blank" rel="noopener noreferrer"><strong>Retrouvez le code complet sur notre Github</strong></a>
<h3>Découvrir les termes associés, pourquoi ?</h3>
Jusqu'ici, nous avons vu comment <strong>visualiser les termes les plus fréquents</strong> (par diagramme en barres ainsi que par nuage de mots), ainsi que des<strong> techniques de nettoyage</strong> de corpus.

Afin d'aller plus loin dans le mining de notre texte, nous nous concentrerons dans ce billet sur l'<strong>étude des relations</strong> entre les différents mots d'un corpus. Cette technique vous permettra de faire émerger de l'information autrement inaccessible via les manipulations de texte expliquées jusqu'ici : nous nous intéressons ici à un niveau supérieur — les relations entre termes. En d'autres termes, quels sont les termes fréquemment associés à une thématique définie ?

[Tweet "#DataScience — #TextMining et corrélation avec #RStats"]
<h3>Obtenir le TermDocumentMatrix utilisé dans notre série</h3>
Le calcul d'association, réalisé par le package <em>tm</em>, s'effectue sur un <em>TermDocumentMatrix</em>, dans R.

Pour rappel, nous travaillons sur le texte de Proust, avec le package {proustr}. <code>
</code>
<h4>findAssocs, créer un vecteur de termes associés</h4>
La fonction findAssocs(), disponible dans le package <em>tm</em>, vous permet de retrouver les termes fréquemment associés à un autre. Cette fonction prend trois arguments :
- x : un <em>TermDocumentMatrix</em>
- terms : un ou plusieurs termes sources
- corlimit : un vecteur numérique, comprenant une limite minimum (comprise entre 0 et 1) de corrélation entre le(s) terme(s) de <em>terms</em> et les autres éléments du corpus.

Notre texte d'exemple comptant une large variété de termes, la limite de corrélation minimum est faible — nous l'avons ici fixée à 0.05.

Afin d'obtenir un dataframe contenant les termes liés :
<pre id="rstudio_console_output" class="GGHFMYIBMOB" tabindex="0"><span class="GGHFMYIBCOB ace_keyword">library("wordcloud")
library("tidyverse")
library("proustr")
library("tidytext")
library("qdapTools")
library("tm")
corpus &lt;- proust_books() %&gt;%
</span> <span class="GGHFMYIBCOB ace_keyword">  mutate(text = stringr::str_replace_all(.$text, "’", " ")) %&gt;% 
</span> <span class="GGHFMYIBCOB ace_keyword">  .$text %&gt;% 
</span> <span class="GGHFMYIBCOB ace_keyword">  VectorSource()%&gt;%
</span> <span class="GGHFMYIBCOB ace_keyword">  VCorpus()%&gt;%
</span> <span class="GGHFMYIBCOB ace_keyword">  tm_map(content_transformer(tolower))%&gt;%
</span> <span class="GGHFMYIBCOB ace_keyword">  tm_map(stripWhitespace) %&gt;%
</span> <span class="GGHFMYIBCOB ace_keyword">  tm_map(removeNumbers)%&gt;%
</span> <span class="GGHFMYIBCOB ace_keyword">  tm_map(removePunctuation)%&gt;%
</span> <span class="GGHFMYIBCOB ace_keyword">  tm_map(removeWords, stopwords("french"))%&gt;%
</span> <span class="GGHFMYIBCOB ace_keyword">  TermDocumentMatrix()</span></pre>
<pre class="GGHFMYIBMOB" tabindex="0"><span class="GGHFMYIBCOB ace_keyword">associations &lt;- findAssocs(corpus, "temps", corlimit = 0.05) %&gt;% 
</span> <span class="GGHFMYIBCOB ace_keyword">  list_vect2df() %&gt;%
</span> <span class="GGHFMYIBCOB ace_keyword">  data.frame()
</span>names(associations) &lt;- c("source", "terme", "corr")
associations &lt;- arrange(associations, desc(corr))</pre>
<h3>Visualiser les termes les plus associés</h3>
Afin de visualiser les termes les plus corrélés avec <em>king</em> et <em>queen</em> dans notre corpus, nous dressons un barplot avec ggplot, en suivant le code suivant :
<pre id="rstudio_console_output" class="GGHFMYIBMOB" tabindex="0"><span class="GGHFMYIBCOB ace_keyword">ggplot(associations[1:10,], aes(x = terme, y = corr)) + 
</span> <span class="GGHFMYIBCOB ace_keyword">  geom_bar(stat="identity") + 
</span> <span class="GGHFMYIBCOB ace_keyword">  coord_flip()+
</span> <span class="GGHFMYIBCOB ace_keyword">  xlab("Terme") + 
</span> <span class="GGHFMYIBCOB ace_keyword">  ylab("Corrélation") + 
</span> <span class="GGHFMYIBCOB ace_keyword">  theme_minimal()</span></pre>
<a href="http://data-bzh.fr/wp-content/uploads/2016/06/correlation_tm.png"><img class="aligncenter wp-image-3560" src="http://data-bzh.fr/wp-content/uploads/2016/06/correlation_tm.png" alt="tm avec R correlation" width="500" height="500" /></a>
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