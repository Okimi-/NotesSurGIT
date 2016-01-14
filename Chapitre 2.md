GIT - Résumé du chapitre 2
==========================

Un remote est un ordinateur possédant une copie du repository. Il sert de sauvegarde au projet. Deux services de Remote :
* Github
* Gitbucket

Récupérer des source depuis un repository

    git clone +URL (en HTTPS)

Envoyer les modifications (github va demander le nom d'utilisateur et le mot de passe)

    git pull origin master

Récupérer les modification apportées sur le Repository

    git pull origin master

Note : Il est conseillé de faire un git pull le matin git push et un git push le soir, pour que l'équipe de développement soit à jour.

En complément
-------------

La documentation de GitBucket indique qu'il est possible de mettre en place un Repository à partir d'un projet déjà existant. Pour lier le Repository au répertoire de travail du projet déjà existant, il faut initialiser GIT comme suit :

    cd /path/to/my/repo
    git remote add origin https://Okimi-@bitbucket.org/Okimi-/testgitcsharp.git
    git push -u origin --all # pushes up the repo and its refs for the first time
    git push -u origin --tags # pushes up any tags
    
