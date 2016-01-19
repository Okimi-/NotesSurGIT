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
CONFLICT (content): Merge conflict in NOM DU FICHIER  
Automatic merge failed; fix conflics and then commit the result.  
