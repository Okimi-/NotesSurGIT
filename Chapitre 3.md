GIT - Chapitre 3
================

Créer des branches
------------------

Créer une nouvelle branche, à partir du point ou l'on se trouve

    git branch NOM_DE_LA_BRANCHE

Basculer sur une branche.  
*Note : Avant de basculer d'une branche à l'autre, il faut faire un "Commit" des modifications sinon le checkout déclenche une erreur.*

    git checkout NOM_DE_LA_BRANCHE
    git checkout master (pour revenir sur la branche maître)
    git checkout -b NOM_DE_LA_BRANCHE (créer la branche et se positionne sur celle-ci)

Voir la liste des branches

    git branch

Supprimer une branche

    git branch -d NOM_DE_LA_BRANCHE

Fusionner des branches
----------------------

Pour fusionner une branche sur la branche maître, il faut se positionner sur la branche master et utiliser la commande

    git merge NOM_DE_LA_BRANCHE

Note : A la suite d'une fusion, la branche fusionnée n'est pas supprimée.

Résoudre un conflit
-------------------

Si le même fichier sur deux branches différentes est modifié, la commande *git merge* lève une erreur  
**CONFLICT (content): Merge conflict in NOM DU FICHIER**  
**Automatic merge failed; fix conflics and then commit the result.**  
Avec le nom du ou des fichiers en conflit. Dans ces fichiers en conflit, les sections de texte qui n'ont pas pu être fusionnées, sont marquées comme ceci :

    <<<<<<<< HEAD
    PARTIE DU FICHIER PRINCIPAL
    =======
    PARTIE DU FICHIER FUSIONNE
    >>>>>>>> modif

Il faut résoudre le conflit *à la main* en conservant (ou pas) les sections de texte. On marque la résolution du conflit à l'aide de la commande

    git commit

Celle-ci va afficher un texte de commit automatique, qu'il ne reste plus qu'a valider. A la suite du *git commit*, les branches sont fusionnées.

Savoir qui a fait une modification
----------------------------------

Pour connaitre la personne qui est à l'origine d'une modification sur un fichier :

    git blame NOM DU FICHIER

Cette commande va retourner toutes les lignes du fichier. Elles sont marquées par les 8 premiers caractères du SHA correspondant au dernier *commit* ayant modifié la ligne. Ces 8 premiers caractères peuvent aussi être utilisés dans la commande *git show* qui montrera plus précisément les modifications du fichier.

    git show 8 PREMIERS CARACTERE DU SHA

Ignorer des fichiers
--------------------

Il est possible d'indiquer à git, des fichiers dont il ne faut pas assurer le suivi. Pour cela, on utilise un fichier de configuration appelé *.gitignore*.

Eviter les Commits supperflus
-----------------------------

Utilisation d'un Commit temporaire pour sauvegarder des modifications

    git stach

Après *git stach*, on revient sur l'état précédent les modifications, sur lequel on peux appliquer des modifications. Et pour revenir à cet état sauvegardée, il suffit d'utiliser

    git stach pop

!!! Attention, l'utilisation de *git statch pop* supprime ce qui a été mis de côté...

Contribuer à des projets Open Source
------------------------------------

Pour proposer des modifcations à un projet (des *PullRequest*), il faut faire une copie de ce projet *un Fork* sur notre propre compte GitHub, puis on créer une branche qui incluera les modifications que l'on veux apporter.  
A la suite des changements et des *Commit*, les modifications sont envoyées sur notre propre GitHub par un

    git push origin NOM_DE_LA_BRANCHE

La branche des modifications peux ensuite être soumise au compte GitHub d'origine par un *Pull Request*, directement sur le site GitHub de notre propre compte.

Exercice : Expliquer GIT
------------------------

GIT est un ensemble de mécanismes qui permettent d'enregistrer et de suivre l'évolution des sources d'un projet informatique, tout au long de son développement. Il n'y a rien de plus simple, il faut seulement déclarer le répertoire contenant les sources du projet comme étant suivi par GIT.  
A chaque modification significative du code source, on déclare à GIT, qu'il faut mémoriser l'évolution en cours. Une mémorisation, en langage GIT s'appelle : un **Commit**. Chaque **Commit** est obligatoirement accompagné d'un texte explicatif des modifications qui ont été apportées.  
Comme cela, au fur et à mesure de l'évolution d'un projet, on peut dire quel développeur a modifié quel(s) fichier(s) et quand. Et il y a même qu'une seule commande suivre les évolutions : *git log*.  

Il faut voir l'évolution d'un projet informatique comme une suite de mémorisations de l'état de ce projet. Mais cette évolution n'est pas linéaire, surtout quand il y a plusieurs développeurs sur le même projet. *Par exemple, un développeur va vouloir mettre en place une fonctionnalité, mais tant qu'elle n'est pas terminée, il ne veut pas diffuser celle-ci.*  
GIT autorise la création de branches, que l'on peut imaginer comme une copie de travail dédiée à des modifications. L'intérêt de celle-ci, c'est qu'un développeur peut réaliser des modifications dans sa branche et si les modifications lui conviennent, elles seront réintégrées dans le projet principal. Au contraire, la fonction développée ne fonctionne pas, la branche est annulée et le développeur retrouve ses sources dans l'état qu'elles étaient avant la création de celle-ci.
