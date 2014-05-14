.. _installation:

############
Installation
############

**********
Pré-requis
**********

Vous devez avoir installer :

- un serveur web (apache, ...)
- PHP
- le moteur de base de donnees MySQL


Sous windows, il est facuile de trouver de la documentation pour l'installation
de ces éléments en utilisant wamp (http://www.wampserver.com/) ou easyphp 
(http://easyphp.fr/) par exemple.

Sous Linux, il est facile de trouver de la documentation pour l'installation de
ces éléments sur votre distribution.


***********
Déploiement
***********

Installation des fichiers de l'applicatif
=========================================

Télécharger l'archive zip
-------------------------

https://adullact.net/frs/?group_id=322


Décompresser l'archive zip dans le répertoire de votre serveur web
------------------------------------------------------------------

Exemple sous windows dans wamp : wamp/www/openresultat
Exemple sous linux avec debian : /var/www/openresultat


Création et initialisation de la base de données
================================================

Créer la base de données
------------------------

Par défaut la base de données s'appelle openresultat.


Initialiser la base de données
------------------------------

Il faut initialiser les tables, les séquences et données de paramétrage :

- data/mysql/init.sql


Initialiser un jeu de données de démonstration (optionnel)
----------------------------------------------------------

Il est possible d'initialiser un jeu de données pour tester l'applicatif avec
des données de démonstration :

- data/mysql/init_demo.sql


Configuration de l'applicatif
=============================

Positionner les permissions nécessaires au serveur web
------------------------------------------------------

Exemple sous linux avec debian : chown -R www-data:www-data /var/www/openresultat


Configuration de la connexion à la base de données
--------------------------------------------------

La configuration se fait dans le fichier `dyn/base.php` :

.. code-block:: php

   // Connexion MySQL
   $conn[1] = array(
       'OpenResultat sur MySQL', // Titre sur la page index.php
       'mysql', // Phptype
       '', // Dbsyntax
       'root', // Remplacer ici le login de l'utilisateur MySQL
       '', // Remplacer ici le mot de passe de l'utilisateur MySQL
       '', // Protocole
       'localhost', // Hote
       '', // Port
       '', // Socket
       'openresultat', // Remplacer ici le nom de la base de données
       'AAAA-MM-JJ' // Format date de la base
   );


*************************
Connexion à l'application
*************************

Ouverture dans le navigateur
============================

http://localhost/openresultat/


Login
=====

* Utilisateur "administrateur" : 
   - identifiant : admin
   - mot de passe : admin
* Utilisateur "démonstration" (si le fichier d'initalisation du jeu de données de démonstration a été appliqué) :
   - identifiant : demo
   - mot de passe : demo

Le message de bienvenue doit être affiché "Votre session est maintenant ouverte."

