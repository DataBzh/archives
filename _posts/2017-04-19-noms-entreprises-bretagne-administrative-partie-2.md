---
ID: 3272
post_title: >
  Noms des entreprises en Bretagne
  administrative – Partie 2
author: Michel Caradec
post_excerpt: ""
layout: post
permalink: >
  http://data-bzh.fr/noms-entreprises-bretagne-administrative-partie-2/
published: true
post_date: 2017-04-19 14:00:47
---
<h2>Ce billet fait suite à un <a href="http://data-bzh.fr/noms-entreprises-bretagne-administrative-partie-1/">premier</a>, dans lequel nous avions commencé à nous intéresser aux noms des entreprises en Bretagne administrative, en travaillant notamment sur les mots.</h2>
<!--more-->[Tweet "#Noms des #entreprises en #Bretagne"]

Nous allons poursuivre dans cette seconde partie en travaillant cette fois sur les <strong>lettres</strong>.
<h2>Données</h2>
Les informations sur les entreprises et leurs établissements proviennent de la <a href="http://www.sirene.fr/">base Sirene</a>, <a href="http://www.data.gouv.fr/fr/datasets/base-sirene-des-entreprises-et-de-leurs-etablissements-siren-siret/">disponible en Open Data</a> sur le site <a href="http://www.data.gouv.fr/">data.gouv.fr</a>.

Les entreprises répertoriées dans ce jeu de données peuvent-être classées en 2 catégories :
<ol>
 	<li>Les entreprises.</li>
 	<li>Les entrepreneurs individuels.</li>
</ol>
Tout comme dans la <a href="http://data-bzh.fr/noms-entreprises-bretagne-administrative-partie-1/">première partie</a> de cette série, nous ne prendrons en compte que les <strong>entreprises</strong>.

Précisons que la base <strong>Sirene</strong> recense le <strong>nom d’exploitation</strong> de la société ainsi que le <strong>nom de l’enseigne</strong>, qui peuvent parfois être différents. C’est le <strong>nom d’exploitation</strong> que nous utiliserons ici.
<h2>Analyse exploratoire</h2>
<a href="http://data-bzh.fr/entreprises-bretagne-administrative/">Rappelons</a> pour commencer que le nombre d’établissements référencés en Bretagne administrative est de <strong>468 108</strong>.

Commençons par l’utilisation des lettres de l’alphabet, en comptabilisant le nombre d’occurrences pour chaque lettre.

<img class="aligncenter size-full wp-image-3276" src="http://data-bzh.fr/wp-content/uploads/2017/04/01-letter_count.png" alt="Fréquence d'utilisation par lettre" width="1200" height="600" />

C’est sans réelle surprise la lettre <strong>e</strong> qui apparaît le plus souvent.

Plus globalement, la fréquence d’apparition des lettres dans le nom des entreprises est-elle similaire à celle observée dans la langue française (qui est plus basée sur du contenu littéraire que sur des appellations) ?

Comparons les deux fréquences d’utilisation :

<img class="aligncenter size-full wp-image-3277" src="http://data-bzh.fr/wp-content/uploads/2017/04/02-letter_freq.png" alt="Fréquences d'utilisation par lettre" width="1200" height="600" />

Vous pouvez vous reporter à la <a href="https://fr.wikipedia.org/wiki/Fréquence_d%27apparition_des_lettres_en_français">fiche Wikipedia</a> correspondante pour plus d’information sur la fréquence d’apparition des lettres en français.

Les fréquences d’utilisation semblent relativement similaires. Essayons de valider statistiquement cette intuition.

La différence de fréquence entre les deux catégories (noms d’entreprises, langue française) pour chaque lettre est comprise entre <strong>0.07%</strong> et <strong>2.57%</strong>, pour une moyenne de <strong>0.86%</strong>.

<img class="aligncenter size-full wp-image-3278" src="http://data-bzh.fr/wp-content/uploads/2017/04/03-letter_freq_verif_boxplot.png" alt="Ecart de fréquence d'utilisation des lettres" width="1200" height="600" />

<em>Pour en savoir plus les boîtes à moustache, se reporter à la <a href="https://fr.wikipedia.org/wiki/Boîte_à_moustaches">fiche Wikipedia</a></em>.

Le <strong>coefficient de corrélation</strong> entre les fréquences est de <strong>0.95</strong> (avec un <strong>interval de confiance</strong> compris entre <strong>0.89</strong> et <strong>0.98</strong>), ce qui est considéré comme élevé (le maximum étant 1).

Observons graphiquement cette corrélation en affichant pour chaque lettre une fréquence d’utilisation (noms sur l’axe des abscisses) par rapport à l’autre (langue française sur l’axe des ordonnées).

<img class="aligncenter size-full wp-image-3279" src="http://data-bzh.fr/wp-content/uploads/2017/04/04-letter_freq_cor.png" alt="Corrélation de la fréquence d'utilisation par lettre" width="1200" height="600" />

<em>Plus une lettre est proche de la ligne en pointillés (qui indique une corrélation parfaite), plus la corrélation est importante.</em>

La représentation graphique vient confirmer la corrélation élevée (<strong>0.95</strong>) qu’il y a dans l’usage des lettres de l’alphabet entre les noms d’entreprises et la langue française.

Terminons avec quelques noms surprenants, dans la mesure où ceux-ci sont composés d’une seule et même lettre, répétée une ou plusieurs fois :
<table>
<thead>
<tr>
<th align="left">Nom</th>
<th align="left">Activité</th>
</tr>
</thead>
<tbody>
<tr>
<td align="left">CC</td>
<td align="left">Autres activités de services</td>
</tr>
<tr>
<td align="left">K</td>
<td align="left">Activités immobilières</td>
</tr>
<tr>
<td align="left">L</td>
<td align="left">Activités immobilières</td>
</tr>
<tr>
<td align="left">AA</td>
<td align="left">Activités de services administratifs et de soutien</td>
</tr>
<tr>
<td align="left">K</td>
<td align="left">Commerce ; réparation d'automobiles et de motocycles</td>
</tr>
<tr>
<td align="left">K</td>
<td align="left">Commerce ; réparation d'automobiles et de motocycles</td>
</tr>
<tr>
<td align="left">DD</td>
<td align="left">Activités immobilières</td>
</tr>
<tr>
<td align="left">O</td>
<td align="left">Activités immobilières</td>
</tr>
<tr>
<td align="left">MMM</td>
<td align="left">Activités immobilières</td>
</tr>
<tr>
<td align="left">55</td>
<td align="left">Activités immobilières</td>
</tr>
<tr>
<td align="left">B</td>
<td align="left">Industrie manufacturière</td>
</tr>
<tr>
<td align="left">H</td>
<td align="left">Activités spécialisées, scientifiques et techniques</td>
</tr>
<tr>
<td align="left">AAA</td>
<td align="left">Activités financières et d'assurance</td>
</tr>
<tr>
<td align="left">K</td>
<td align="left">Construction</td>
</tr>
<tr>
<td align="left">K</td>
<td align="left">Activités immobilières</td>
</tr>
<tr>
<td align="left">H</td>
<td align="left">Activités immobilières</td>
</tr>
</tbody>
</table>
<h2>Conclusion</h2>
On le constate, les noms des entreprises peuvent faire l’objet de nombreuses études, qu’elles soient informatives ou plus anecdotiques.

Les idées et sujets d’exploration ne manquent donc pas, et seront, qui sait, peut-être un prétexte à un troisième billet sur le sujet…

Le code <strong>R</strong> utilisé pour la rédaction de cet article ainsi que du <a href="http://data-bzh.fr/noms-entreprises-bretagne-administrative-partie-1/">précédent</a> est disponible sur notre dépôt de sources <a href="https://github.com/DataBzh/territoire/tree/master/nomsentreprises">Github</a>.