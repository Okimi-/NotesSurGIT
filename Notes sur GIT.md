
GIT - Résumé du chapitre 1
==========================

GIT (proconcer GUITE), a été crée en 2005 par Linus Torvald. C'est un logiciel de versionning distribué.
Le repository est enregistré en local, dans le répertoire de travail.

Vocabulaire : 1 Commit = 1 Validation

Définir de manière globale ( sur l'ordinateur), l'utilisateur en cours et le mot de passe
  git config --global user.name "Votre nom ou pseudo"
  git config --global user.email "Votre@email.com"

Pour définir un répertoire comme répertoire GIT, utiliser la commande :
  git init

Ajouter un fichier
  git add	"NONDUFICHIER"

Ajoute de tous les fichiers modifiés
  git commit -m "MESSAGE"
  git commit -am "MESSAGE"
  
Affiche la liste les changements des différentes validations (COMMIT)
  git log						Liste les changements des commits

Pour se positionner sur une version des sources  
  git checkout xxxxx (SHA)
  git checkout master

Note : A la différente de la gestion des versions intégrée à WinDev, il faut, dans GIT, deux commandes pour réintégrer un fichier modifié dans le repository (un add et un commit).

GIT - Résumé du chapitre 2
==========================

Un remote est un ordinateur possédant une copie du repository. Il sert de sauvegarde au projet.
Deux services de Remote :
* Github
* Gitbucket

Récupérer des source depuis un repository :
  git clone +URL (en HTTPS)

Envoyer mes modifications (github va demander le nom d'utilisateur et le mot de passe)
  git pull origin master

Récupérer les modification apportées sur le Repository
  git pull origin master

Idéalement, il est conseillé de faire un git pull le matin git push et un git push le soir, pour que l'équipe de développement soit à jour.

En complément de ce chapitre 2
La documentation de GitBucket indique qu'il est possible de mettre en place un Repository à partir d'un projet déjà existant. Pour lier le Repository au répertoire de travail du projet déjà existant, il faut initialiser GIT comme suit :

cd /path/to/my/repo
git remote add origin https://Okimi-@bitbucket.org/Okimi-/testgitcsharp.git
git push -u origin --all # pushes up the repo and its refs for the first time
git push -u origin --tags # pushes up any tags
