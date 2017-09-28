---
ID: 414
post_title: 'Premiers pas en text-mining avec R &#8211; Partie 1'
author: Colin FAY
post_excerpt: ""
layout: post
permalink: http://data-bzh.fr/text-mining-r-part-1/
published: true
post_date: 2016-03-20 18:00:35
---
<h2>Appelé "Fouille de textes" dans la langue de Molière, le text-mining désigne le traitement d'un texte en vue d'en faire émerger des informations. Comment le réaliser avec R ?</h2>
<!--more-->

<em>Note — Ce billet fait partie d'une série de billets sur le text-mining avec R. Nous vous invitons à les consulter dans l'ordre :</em>
<em>- <a href="http://data-bzh.fr/text-mining-r-part-1/" target="_blank" rel="noopener noreferrer">Premiers pas en text-mining avec R – Partie 1</a></em>
<em>- <a href="http://data-bzh.fr/text-mining-r-part-2/" target="_blank" rel="noopener noreferrer">Premiers pas en text-mining avec R – Partie 2</a></em>
<em>- <a href="http://data-bzh.fr/text-mining-r-part-3/" target="_blank" rel="noopener noreferrer">Premiers pas en text-mining avec R – Partie 3
</a>- <a href="http://data-bzh.fr/text-mining-r-part-4/" target="_blank" rel="noopener noreferrer">Premiers pas en text-mining avec R - Partie 4</a></em>
<h3>Le text-mining, c'est quoi ?</h3>
Discipline au croisement de la linguistique, de l'informatique et des statistiques, le text-mining permet <strong>l'analyse automatique d'un corpus de textes</strong>, afin d'en faire émerger des patterns, des tendances et des singularités. Une technique que nous croisons tous les jours — prenez par exemple le traitement des spams : en analysant les contenus textuels des messages que vous recevez, l'algorithme est en mesure de trier et de détecter si oui ou non un nouveau mail vous intéresse.

En text-mining, on distingue deux étapes : d'abord, l'<strong>analyse</strong>, permettant de reconnaître automatiquement les mots, leur type, leur rôle, mais également leur fréquence et leur relation. Ensuite, l'<strong>interprétation</strong>, visant à faire émerger du sens de l'analyse. Dans le cas de la détection de spam, l'algorithme analyse dans un premier temps le contenu, avant d'opérer un tri dans votre boîte de réception après avoir interprété les résultats de l'analyse.

[Tweet "#DataScience — Introduction au #TextMining avec #RStats"]
<h3>Premiers pas en text-mining : l'analyse fréquentielle</h3>
Comme son nom l'indique, l'analyse fréquentielle permet de <strong>définir la fréquence d'apparition d'une unité au sein du corpus</strong> global. Autrement dit, une fois cette opération effectuée, vous serez en mesure de définir quels sont les mots les plus utilisés dans un texte.

Pourquoi calculer la fréquence ? Dans les faits, c'est une <strong>technique riche en information</strong>. Prenons l'exemple d'un corpus de livres d'un même auteur : l'analyse de fréquence vous permet d'avoir une <strong>liste complète des thématiques abordées dans la bibliographie</strong>  de l'écrivain, via les mots les plus utilisés dans l’œuvre.

Afin de nettoyer le corpus, il est indispensable de passer par la suppression des <strong>"stopwords" ou mots vides, qui sont des mots extrêmement communs</strong>, et qui n'apportent aucune information valable à votre interprétation. Concrètement, vous retrouvez dans cette liste les mots comme "le", "du", "ce" (pour la langue française), et bien d'autres de la famille des articles, des pronoms et des prépositions. Attention, cette liste n'est pas universelle : une sélection de mots vides pour un corpus se fait en fonction du but poursuivi, de la question à laquelle répond l'analyse — la fréquence d'apparition du "je" peut être une information pertinente à certaines analyses et ne pas l'être pour d'autres, il ne s'agit donc pas de s'en séparer trop vite !
<h3>Text-mining avec R, quelques lignes de code</h3>
Pour exemplifier le fonctionnement du text-mining avec le logiciel R, nous avons choisi d'analyser l'oeuvre de Proust "À la recherche du temps perdu", disponible dans le package {<a href="https://cran.r-project.org/web/packages/proustr/index.html" target="_blank" rel="noopener noreferrer">proustr</a>}.

Dans ce billet, nous allons vous présenter deux méthodes de text-mining — la "classique", et celle du tidytext. Commençons par charger les packages.
<code></code>
<pre id="rstudio_console_output" class="GGHFMYIBMOB" tabindex="0"><span class="GGHFMYIBCOB ace_keyword">library("tm")
</span><span class="GGHFMYIBCOB ace_keyword">library("tidytext")
</span><span class="GGHFMYIBCOB ace_keyword">library("proustr")
</span><span class="GGHFMYIBCOB ace_keyword">library("tidyverse")
</span><span class="GGHFMYIBCOB ace_keyword">devtools::install_github("ThinkRstat/stopwords")
</span><span class="GGHFMYIBCOB ace_keyword">library("stopwords")</span></pre>
<h4>Étape 0  : Chargement du document</h4>
<pre id="rstudio_console_output" class="GGHFMYIBMOB" tabindex="0"><span class="GGHFMYIBCOB ace_keyword">books &lt;- proust_books()</span></pre>
<h4>Méthode 1.1  : Tidytext</h4>
Nous commençons par utiliser la méthode du tidytext, décrite dans l'ouvrage "<a href="http://tidytextmining.com/" target="_blank" rel="noopener noreferrer">Tidy Text-mining with R</a>".

<code></code>
<pre id="rstudio_console_output" class="GGHFMYIBMOB" tabindex="0"><span class="GGHFMYIBCOB ace_keyword">books_tidy &lt;- proust_books() %&gt;%
</span> <span class="GGHFMYIBCOB ace_keyword">  mutate(text = stringr::str_replace_all(.$text, "’", " ")) %&gt;% 
</span> <span class="GGHFMYIBCOB ace_keyword">  unnest_tokens(word, text) %&gt;%
</span> <span class="GGHFMYIBCOB ace_keyword">  filter(!word %in% stopwords_iso$fr) %&gt;%
</span> <span class="GGHFMYIBCOB ace_keyword">  count(word, sort = TRUE) %&gt;%
</span> <span class="GGHFMYIBCOB ace_keyword">  head(10)</span></pre>
<h4>Méthode 1.2  : Visualisation</h4>
<code></code>
<pre id="rstudio_console_output" class="GGHFMYIBMOB" tabindex="0"><span class="GGHFMYIBCOB ace_keyword">barplot(height=books_tidy$n, names.arg= books_tidy$word, xlab="Mots", ylab="Fréquence", col="#973232", main="À la recherche du temps perdu")</span></pre>
<code>
</code>

<a href="http://data-bzh.fr/wp-content/uploads/2016/03/tidy_analysis.png"><img class="aligncenter size-full wp-image-3550" src="http://data-bzh.fr/wp-content/uploads/2016/03/tidy_analysis.png" alt="Tidy text mining avec R" width="1200" height="600" /></a>
<h4>Méthode 2.1 : Méthode classique</h4>
Pour travailler avec cette méthode, il faut commencer par transformer le texte en corpus.
<pre id="rstudio_console_output" class="GGHFMYIBMOB" tabindex="0"><span class="GGHFMYIBCOB ace_keyword">corpus &lt;- proust_books() %&gt;%
</span> <span class="GGHFMYIBCOB ace_keyword">  mutate(text = stringr::str_replace_all(.$text, "’", " ")) %&gt;% 
</span> <span class="GGHFMYIBCOB ace_keyword">  .$text %&gt;% 
</span> <span class="GGHFMYIBCOB ace_keyword">  VectorSource()%&gt;%
</span> <span class="GGHFMYIBCOB ace_keyword">  VCorpus()</span></pre>
<h4>Étape 2.2 : Nettoyage du corpus</h4>
<pre id="rstudio_console_output" class="GGHFMYIBMOB" tabindex="0"><span class="GGHFMYIBCOB ace_keyword">corpus &lt;- corpus %&gt;%
</span> <span class="GGHFMYIBCOB ace_keyword">  tm_map(content_transformer(tolower))%&gt;%
</span> <span class="GGHFMYIBCOB ace_keyword">  tm_map(stripWhitespace) %&gt;%
</span> <span class="GGHFMYIBCOB ace_keyword">  tm_map(removeNumbers)%&gt;%
</span> <span class="GGHFMYIBCOB ace_keyword">  tm_map(removePunctuation)%&gt;%
</span> <span class="GGHFMYIBCOB ace_keyword">  tm_map(removeWords, stopwords("french"))</span></pre>
Cette étape permet de nettoyer le corpus des différentes mises en forme qui pourraient interférer à notre analyse : d'abord, une mise en minuscule de tous les mots (rappelons que R est sensible à la casse), puis une suppression des espaces vides, enfin, une suppression des mots vides.

<code></code>

Vous pouvez également retirer des mots précis :
<pre id="rstudio_console_output" class="GGHFMYIBMOB" tabindex="0"><span class="GGHFMYIBCOB ace_keyword">corpus &lt;- tm_map(corpus, removeWords, c("mot1", "mot2"...))</span></pre>
<span style="font-size: 1rem; font-weight: 800;">Étape 3 : Création d'une matrice des fréquences</span>

<code></code>
<pre id="rstudio_console_output" class="GGHFMYIBMOB" tabindex="0"><span class="GGHFMYIBCOB ace_keyword">TDM &lt;- corpus %&gt;%
</span> <span class="GGHFMYIBCOB ace_keyword">  TermDocumentMatrix() %&gt;%
</span> <span class="GGHFMYIBCOB ace_keyword">  as.matrix()
</span><span class="GGHFMYIBCOB ace_keyword">TDM &lt;- sort(rowSums(TDM),decreasing=TRUE)
</span><span class="GGHFMYIBCOB ace_keyword">TDM &lt;- data.frame(word = names(TDM),freq=TDM)</span></pre>
Ces commandes renvoient les termes les plus fréquents dans notre corpus.
<h4>Étape 4 : Visualisation des 10 mots les plus fréquents</h4>
<pre id="rstudio_console_output" class="GGHFMYIBMOB" tabindex="0"><span class="GGHFMYIBCOB ace_keyword">barplot(height=head(TDM,10)$freq, names.arg=head(TDM,10)$word, xlab="Mots", ylab="Fréquence", col="#973232", main="À la recherche du temps perdu")</span></pre>
<a href="http://data-bzh.fr/wp-content/uploads/2016/03/tm_text_mining.png"><img class="aligncenter size-full wp-image-3551" src="http://data-bzh.fr/wp-content/uploads/2016/03/tm_text_mining.png" alt="tm text mining R" width="1200" height="600" /></a>

Code complet

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