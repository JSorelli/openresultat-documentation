.. _mises_a_niveau:

##############
Mises à niveau
##############


Mettre à niveau openRésultat de 1.13 vers 1.14
==============================================

* Sauvegarder les fichiers de l'applicatif ainsi que la base de données.

* Appliquer le script de mise à jour de la base de données 
  `data/mysql/ver_1.14.sql`.

* Déplacer tous les fichiers .pdf du répertoire `pdf/` vers le répertoire 
  `tmp/`.::

   mv pdf/*.pdf tmp/

* Déplacer tous les répertoires de résultats générés à la racine du répertoire
  `aff/` vers le répertoire `aff/res/`.::

   mv aff/REF* aff/res/
   mv aff/PRE* aff/res/
   ...

* Configurer le nouvel affichage web.

* ...