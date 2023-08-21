# generateur_QRcode
---- PARTIE 1 ----
#commande d'installation des outils(avec connexion internet)
python -m pip install -r requirements.txt

#commande pour verifier installation
django-admin --version

#debut de creation du projet
django-admin startproject generateur

#on rentre dans le projet creer et on ouvre visual studio
#on configure le fichier settings.py qui se trouve dans le dossier generateur
#on descend jusquu'a la ligne 106 oû se trouve LANGUAGE_CODE
#on remplace 'en-US' par 'fr-FR'

# on damare le serveur
python manage.py runserver

#on ouvre un navigateur telque chrome ou edge puis on saisi dans la bare de recherche
# localhost:8000

******* creation d'une application************
"python manage.py startapp nom_appli"

#pour que le projet prend en compte notre app, ond doit ajouter le nom de notre app
#sur la liste INSTALLED_APPS dans le fichier seting.py
#codage d'application:
~~~~configuration des templates~~~~: 
	pour qu'ils soient accessible,dans chaque application on doit
	-créer un dossier qui s'appel 'templates' dans ce dossier on crée un dossier qui a même nom 
	-que l'application,c'est dans ce dossier qu'on doit mettre tous nos fichiers html
-
~~~~~~~~~configuration des fichiers static:~~~~~~~~~~~~~~
	pour charger les fichier static,il y a deux methodes:

1ere methode:
	on crée à la racine de notre projet un dossier qui a pour nom 'static'
	dans ce dossier on crée 4 sous dossiers :
	 -js
	 -css
	 -imgaes
	 -video	
	faire reconnaitre les dossier  à notre projet,on rentre dans seting.py
	aprés la variable STATIC_URL(119) on crée une variable
	" STATICFILLES = BASE_DIR / 'static' "

****************** codage de l'application *******************************
explication des dossier et fichier

_paycache_: c'est le dossier qui contient tous les fichiers caches(anciens traitements)
migrations: c'est le dossier qui content touts les fichiers de migration permettant de créer la base de données;
__ init__.py: indique que le projet est un projet django/python
admin: c'est le fichier qui contient toutes le configuration et personnalisations de l'interface adminstrateur
apps: c'est le fichier qui contient toutes les configurations de l'application
models: c'est le fichier qui contient toutes les tables liées à cette application
tests: c'est le fichier qui contient toutes les textes unitaires
views: c'est le fichier qui contient toutes les requêtes, il joue le rôle de contrôleur.


#creation de la première page:

le premier élément à configurer est le fichier urls qui se trouve dans le dossier de configuraton du projet,
il faut donc créer un fichier urls.py dans chaque application,on fait la liaison des fichiers urls
en incluant tous les fichiers urls des applications dans le fichier urls dans le dossier de configuration,
dans fichier on importe le module 'include' en fin dans la variable urlpaterns on ajoute à la fin
 "path('generateur-qrcode/',include(cryptage.urls)),"


#pour créer une page on doit configurer deux fichiers qui se trouve dans l'application:
-urls.py et views.py, anvat cela on crée le fichier html à afficher dans le template de l'appli
 puis on crée une fonction  qui renvoie la page html qu'on a crée, et on associe une urls à cette
fonction créée.

***** Quelques methode de selection************
on lance le shell: python manage.py shell.
Puis on saisie:  form nom_appli.models
creation: nom_var=nom_class.objects.create(atribut=....,...);
pour enregistrer: nom_var.save().
___________ quelques operations:__________________________
afficher tous les élements: nom_table.objects.all()

_________ les filtres: _________________
nom_classe.object.filter(champ=val) :permet de filtrer par champ
nom_classe.object.filter(champ__contains=val):affiche le champ contenat val
nom_classe.object.filter(champ__startswith=val):affiche le champ qui commence par val
nom_classs.object.filter(champ__endswith=val):affiche le champ qui termine par val.
Acceder a un champ d'une clé etrangère: nom_champ-cléetrangère__nom champaAfficher
