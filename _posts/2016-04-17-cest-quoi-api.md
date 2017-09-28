---
ID: 635
post_title: 'Dis, c&rsquo;est quoi une API ?'
author: Colin FAY
post_excerpt: ""
layout: post
permalink: http://data-bzh.fr/cest-quoi-api/
published: true
post_date: 2016-04-17 18:00:22
---
<h2>Contraction de <i><span class="lang-en" lang="en" xml:lang="en">Application Programming Interface</span></i>, l'API est une interface de programmation utilisée pour faire communiquer deux logiciels.</h2>
<!--more-->
<h3>Une API — définition</h3>
En créant une API, un logiciel A (le fournisseur) ouvre une interface qui permet à un autre logiciel B (le consommateur) d'interagir avec lui, en<strong> autorisant l'accès à une partie de ses fonctionnalités </strong>: le logiciel ouvrant son API laisse rarement (voire jamais) ouvert l'ensemble de son contenu. Les API sont au contraire prévues pour cibler uniquement certaines parties du fournisseur. Une fois connectés, les deux logiciels communiquent via des instructions, en suivant une série de <strong>règles (un langage) définies par le fournisseur</strong> — grâce à l'API, B peut envoyer des requêtes dans l'interface de A.

L'objectif ?<strong> Permettre à différents services de communiquer les uns avec les autres de manière simplifiée</strong>, et en temps réel — notamment pour les API web, qui ouvrent l'accès à des données contenues sur un serveur distant. En pratique, un serveur donne accès à sa base, dans lequel <strong>un logiciel tiers peut venir piocher, à condition qu'il parle la bonne langue</strong> : celle définie par le fournisseur. Raison pour laquelle chaque API s'accompagne d'une documentation, qui est un mode d'emploi contenant le <strong>vocabulaire précis pour que les deux communiquent</strong>.
<h3>Et concrètement, une API, ça sert à quoi ?</h3>
Par exemple, imaginez un instant que vous souhaitiez offrir un service de localisation sur votre application mobile ou votre site. Plutôt que de programmer vous-même un service de carte, <strong>vous pouvez connecter votre solution à l'interface</strong> de Google Map, programmer une série de requêtes, et vous aurez, directement sur votre produit, les informations du géant du web. Sans API, vous devriez programmer, vous-même, l'ensemble de la carte interactive de Google Map... Plus facile à dire qu'à faire !

Autre exemple, Facebook : en connectant votre logiciel de traitement de données (<a title="Logiciel — Découvrez R" href="http://data-bzh.fr/logiciel-r/">par exemple R</a>) à une API Facebook, il est possible d'effectuer <strong>une série de requêtes pour obtenir des données publiques</strong>. Par exemple, les informations d'une page : la liste des derniers statuts, le nombre de likes et de partages sur chaque publication, le volume d'abonnés, etc. En créant un <strong>pont entre votre logiciel et l'API du réseau social</strong>, vous êtes en mesure d'entrer les commandes (en suivant le vocabulaire défini par Facebook) pour avoir accès à ces informations publiques. Et il vous sera même possible de poster sur votre propre profil ! Parce qu'en effet, une API ne sert pas uniquement à obtenir des données, mais également à écrire ou exécuter des actions sur le logiciel fournisseur.

À noter que la plupart des réseaux sociaux possèdent une interface ouverte, vous permettant d'obtenir des listes de données. Et beaucoup d'autres : météo, bourse, cartes... De nombreux services offrent une interface de connexion. À vous de fouiller le web !