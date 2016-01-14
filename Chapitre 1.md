
GIT - Résumé du chapitre 1
==========================

GIT (proconcer GUITE), a été crée en 2005 par Linus Torvald. C'est un logiciel de versionning distribué.
Le repository est enregistré en local, dans le répertoire de travail.

Vocabulaire : 1 Commit = 1 Validation

Pour configurer GIT De manière globale sur l'ordinateur

    git config --global user.name "Votre nom ou pseudo"
    git config --global user.email "Votre@email.com"

Définir un répertoire comme répertoire suivit par GIT

    git init

Ajouter un fichier que GIT doit suivre

    git add	"NONDUFICHIER"

Valide les fichiers modifiés

    git commit -m "MESSAGE"
    git commit -am "MESSAGE"
  
Affiche la liste les changements des différentes validations (COMMIT)

    git log

Pour se positionner sur une version des sources

    git checkout xxxxx (SHA)
    git checkout master
