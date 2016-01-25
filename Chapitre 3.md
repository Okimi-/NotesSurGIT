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

Voir la liste des branches

    git branch

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

Après le git stach, on revient sur l'état précédent les modifications, sur lequel on peux appliquer des modifications. Et pour revenir à cet état sauvegardée, il suffit d'utiliser

    git stach pop

