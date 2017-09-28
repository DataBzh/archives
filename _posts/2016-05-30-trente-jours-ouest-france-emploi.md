---
ID: 966
post_title: 30 jours sur Ouest France Emploi
author: Colin FAY
post_excerpt: ""
layout: post
permalink: >
  http://data-bzh.fr/trente-jours-ouest-france-emploi/
published: true
post_date: 2016-05-30 18:00:31
---
<h2>Analyse des données collectées sur l’alerte "Bretagne" du flux RSS de Ouest France Emploi, entre le 29 février et le 29 mars.</h2>
<!--more-->
<h3>À propos de ces données</h3>
Ces données ont été collectées sur le flux RSS de Ouest France Emploi, réglé sur une alerte "Bretagne", entre le 29 février à midi et le 29 mars (à 10:05 du matin) — soit <strong>un total de 3334 annonces</strong>.
<h3>Annonces quotidiennes</h3>
En moyenne, 111 nouvelles annonces ont été publiées chaque jour sur cette alerte Ouest France Emploi — avec un maximum de 196, atteint le 4 mars, et un minimum de 10 le 27 mars.

<a href="http://dev.data-bzh.fr/wp-content/uploads/2016/05/annonce-ouest-france-2.jpeg"><img class="aligncenter size-full wp-image-967" src="http://dev.data-bzh.fr/wp-content/uploads/2016/05/annonce-ouest-france-2.jpeg" alt="Annonces quotidiennes sur Ouest France Emploi" width="1200" height="600" /></a>Nous constatons que, sur les quatre semaines, le volume de publications suit un schéma régulier, avec des publications en semaine, suivi d’une chute les deux jours de week-end.
<h3>Les titres des annonces</h3>
Parmi les titres d’annonces, le <strong>terme le plus fréquent est "intérim"</strong> — une présence très forte laissant entrevoir une forte récurrence de ce type de contrat au sein de notre groupe d'annonces. Nous remarquons également une <strong>large présence de "groupe"</strong>, sous-entendant que ce sont majoritairement les groupes qui emploient le plus au mois de mars.

L’analyse de fréquence nous permet de<strong> classer les départements qui sont le plus utilisés</strong> dans les titres — d’abord, l’Ille-et-Vilaine, avec 396 occurrences de Ille et 408 de Vilaine, puis les Côtes-d’Armor, avec 239 et 270 occurrences, puis le Morbihan (174 oc.) et enfin le Finistère (141 oc.).

Les termes affichant plus de 100 occurrences dans les titres d’annonces :

<a href="http://dev.data-bzh.fr/wp-content/uploads/2016/05/analyse-titres-annonces-mars-2.jpeg"><img class="aligncenter size-full wp-image-976" src="http://dev.data-bzh.fr/wp-content/uploads/2016/05/analyse-titres-annonces-mars-2.jpeg" alt="Analyse des titres des annonces en mars" width="1200" height="600" /></a>Si nous analysons l’<strong>aperçu des annonces disponible dans le flux RSS</strong> (affichant le début des textes, avec une moyenne de 123 caractères), nous trouvons les mots suivants :

<a href="http://dev.data-bzh.fr/wp-content/uploads/2016/05/mots-annonces-ouest-france-emploi-2.jpeg"><img class="aligncenter size-full wp-image-977" src="http://dev.data-bzh.fr/wp-content/uploads/2016/05/mots-annonces-ouest-france-emploi-2.jpeg" alt="Wordmining des textes des annonces" width="1200" height="600" /></a>Ici encore, "intérim" arrive en tête de liste — il s’agit du terme le plus utilisé dans les premiers caractères des annonces du site sur le mois. Nous retrouvons également le vocabulaire introductif classique de l’annonce pour un emploi, avec "recherchons" et "recherche".
<h3>Web-mining des pages</h3>
Avec R, nous avons lancé une requête sur les 3334 urls que nous avons tirées de cette collecte. Une fois toutes ces pages listées, nous avons trié les en-têtes normalisés du site Ouest-France Emploi, contenant les informations suivantes :
<em>Date de publication / Entreprise / Référence / Nombre de postes / Localisation / Contrat / Expérience</em>

Tous les sous-titres n’étant pas remplis sur chaque annonce, nous avons inséré des NA sur les données manquantes. Le dataset final, contenant ces 7 informations pour les 3334 annonces, nous permet de dresser les tendances suivantes :
<h4>Les entreprises qui ont recruté</h4>
Au total, <strong>662 entreprises différentes sont présentes </strong>dans l’entrée du même nom dans notre dataset. Les 10 entreprises qui ont le plus recruté sont :
<h3><a href="http://dev.data-bzh.fr/wp-content/uploads/2016/05/entreprises-recrutements-2.jpeg"><img class="aligncenter size-full wp-image-981" src="http://dev.data-bzh.fr/wp-content/uploads/2016/05/entreprises-recrutements-2.jpeg" alt="10 entreprises qui ont proposé le plus de postes" width="1200" height="600" /></a></h3>
<h4>Types de contrats proposés</h4>
<h4><a href="http://dev.data-bzh.fr/wp-content/uploads/2016/05/volume-contrat-2.jpeg"><img class="aligncenter size-full wp-image-990" src="http://dev.data-bzh.fr/wp-content/uploads/2016/05/volume-contrat-2.jpeg" alt="Volume de contrat en fonction du type" width="1200" height="600" /></a></h4>
Comme nous l’avions déduit depuis les titres des annonces et les aperçus du flux, <strong>l’Interim est le type de contrat le plus demandé du mois</strong>. Les CDI sont, dans les données à notre disposition, plus proposés que les CDD.
<h4>Volume d’annonces en fonction du niveau d’étude requis</h4>
<h4><a href="http://dev.data-bzh.fr/wp-content/uploads/2016/05/volume-annonces-niveau-etude-2.jpeg"><img class="aligncenter size-full wp-image-992" src="http://dev.data-bzh.fr/wp-content/uploads/2016/05/volume-annonces-niveau-etude-2.jpeg" alt="Volume d'annonces en fonction du niveau d'étude requis" width="1200" height="600" /></a></h4>
Les niveaux d’étude les plus demandés sur le mois sont : BEP/CAP et le Bac + 2 — le niveau Bac + 1 et +4 sont les moins demandés.
<h4>Contrat proposé en fonction du niveau d’étude requis</h4>
<a href="http://dev.data-bzh.fr/wp-content/uploads/2016/05/contrat-niveau-etude-2.jpeg"><img class="aligncenter size-full wp-image-983" src="http://dev.data-bzh.fr/wp-content/uploads/2016/05/contrat-niveau-etude-2.jpeg" alt="Contrat en fonction du niveau d'étude" width="1200" height="600" /></a>

Ce graphique nous affiche la<strong> répartition des niveaux d’étude requis en fonction du type de contrat proposé</strong>. La proportion grise représente des données non disponibles — une absence qui peut être liée à deux facteurs : aucun niveau d’étude particulier n’est requis pour occuper le poste, ou l’information n’a pas été remplie sur le site de Ouest-France Emploi.

Nous remarquons que les contrats en intérim sont majoritairement proposés à des titulaires de BEP/CAP, là où il y en a peu en CDI ou CDD, du moins pour la part que nous connaissons. Aucun contrat en intérim n’est proposé pour des titulaires de Bac +5.
<h4>Contrat en fonction du jour du mois</h4>
<h3><a href="http://dev.data-bzh.fr/wp-content/uploads/2016/05/type-contrat-jour-2.jpeg"><img class="aligncenter wp-image-984" src="http://dev.data-bzh.fr/wp-content/uploads/2016/05/type-contrat-jour-2.jpeg" alt="Type de contrat par jour" width="743" height="372" /></a></h3>
Comme découvert précédemment, l’Interim est le type de contrat le plus demandé du mois — nous trouvons des annonces en intérim ainsi qu’en CDI tous les jours de la période étudiées.
<h4>Expérience demandée en fonction du contrat</h4>
<h3><a href="http://dev.data-bzh.fr/wp-content/uploads/2016/05/experience-type-contrat-2.jpeg"><img class="aligncenter size-full wp-image-989" src="http://dev.data-bzh.fr/wp-content/uploads/2016/05/experience-type-contrat-2.jpeg" alt="Expérience demandée en fonction du contrat" width="1200" height="600" /></a></h3>
En CDD, les contrats acceptent majoritairement des débutants — là où les CDI et l’intérim demandent en grande partie une expérience de 3 ans ou plus.
<h3>Les 50 métiers les plus demandés, selon les urls</h3>
Si nous travaillons uniquement sur les titres des annonces, nous avons trop de bruit pour déterminer <strong>les métiers les plus récurrents dans le corpus</strong>. Nous nous sommes donc concentrés sur les urls, qui sont normalisées sur le site sous la forme :

<em>http://www.ouestfrance-emploi.com/offre-d-emploi/NOM-DU-MÉTIER-(h-f)-CHIFFRES/</em>

Nous avons nettoyé ces adresses en retirant de <em>http://www.ouestfrance-emploi.com/offre-d-emploi/</em> d’un côté, et <em>CHIFFRES/ </em>de l’autre — nous avons ensuite supprimé "h-f-", "h-", "-f" et "-f-h", ainsi que des éléments d’urls non normalisés, comme "un-" ou encore "urgent-", présents au début de certaines adresses. Ce tri nous a permis d'obtenir une liste de métiers, sous la forme <em>nom-du-métier</em>.

Au total,<strong> 1353 métiers différents ont été proposés sur le flux RSS de Ouest France Emploi au mois de mars</strong>. Les 5 les plus demandés sont :
<ul>
 	<li>Technicien de maintenance, avec 48 occurrences</li>
 	<li>Serveur / serveuse de restaurant, 34 oc.</li>
 	<li>Cuisinier / Cuisinière, 33 oc.</li>
 	<li>Comptable, 31 oc.</li>
 	<li>Conducteur de ligne, 27 oc.</li>
</ul>
Voici la liste des 50 métiers les plus demandés sur les titres :
<h3><a href="http://dev.data-bzh.fr/wp-content/uploads/2016/05/metiers-demandes-mars-ouest-france-emploi-2.jpeg"><img class="aligncenter size-full wp-image-973" src="http://dev.data-bzh.fr/wp-content/uploads/2016/05/metiers-demandes-mars-ouest-france-emploi-2.jpeg" alt="Les 50 métiers les plus demandés" width="600" height="1200" /></a></h3>
<h3></h3>
<h3>En conclusion — Portrait robot de l’annonce postée en mars sur Ouest-France Emploi</h3>
Au mois de mars, le profil type de l'annonce sur Ouest-France emploi aura été : un poste intérimaire de technicien en maintenance, en Ille-et-Vilaine, avec un niveau d’étude minium de BEP/CAP et 3 à 5 ans d’expérience.