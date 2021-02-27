# Aide aux commandes Git

Voici une feuille récapitulative des différentes commandes Git régulièrement utilisées.
&nbsp;
&nbsp;

|Description|Méthode|Exemple|
|-|-|-|
|**Initialiser un *repository***|`git init`|
|Permet de **pointer le dépot local vers un dépot distant**|`git remote add [nom pour appeler le repo] [URL]`|git remote add OC https://github.com/OpenClassrooms-Student-Center/ProjetOpenSource.git|
|**Cloner un *repository***|`git clone [HTTPS/SSH endpoint]`|git clone https://github.com/OpenClassrooms-Student-Center/ProjetOpenSource.git|
|**Lister les branches**. L'étoile (symbole : *) qui se situe près du nom d'une branche signifie la branche sur laquelle on se situe|`git branch`||
|**Créer une branche**|`git branch [nom de notre branche]`|git branch test|
|**Basculer sur une branche**|`git checkout [nom de notre branche]`|git checkout test|
|**Créer une branche et basculer dessus**|`git checkout -b [nom de notre branche]`|git checkout -b test2|
|**Supprimer une branche**|`git branch -d [nom de notre branche]`|git branch -d test2|
|**Forcer** la **suppression d'une branche** (i.e. avec des modifications dessus)|`git branch -D [nom de notre branche]`||
|**Stager des modifications avant de les ajouter au *repository***|`git add [les fichiers que je souhaite stager/indexer]`|git add src/config/config.yaml|
|**Archiver des modifications**|`git commit`||
|**Archiver des modifications avec un message**|`git commit -m <string>`|git commit -m "Mon super message"|
|**Supprimer le dernier commit d'une branche en local**|`git reset --hard HEAD^`||
|**Remiser un commit supprimé d'une branche en local sur une autre branche**|`git reset --hard [les 8 premiers caractères du hash]`|git reset --hard ca83a6df|
|**Modifier le message du dernier commit** (attention : fonctionne quand il y a aucune modification)|`git commit --amend -m <string>` *(l'argument --amend permet de modifier le dernier commit)*|git commit --amend -m "Mon nouveau super message"|
|**Ajouter un fichier au dernier commit**|Deux étapes : `git add monFichierOublie.txt`*(1)* et `git commit --amend --no-edit`*(2, --no-edit pour ne pas modifier le message)* ||
|**Annuler un commit public** (note : cela créer un nouveau commit qui écrase l'ancien pour ne pas réécrire l'historique)|`git revert [SHA ou HEAD^ pour le dernier commit]`||
|**Observer les derniers commits**|`git log`||
|**Afficher toutes les actions et leurs *SHA* dans l'historique *Git***| `git reflog`||
|**Afficher l'état de nos fichiers**, i.e. où se situe nos fichiers dans les 3 zones loacales majeures (Working Directory, Stage ou Repository)|`git status`||
|**Créer une remise** des modifications|`git stash`||
|**Appliquer une remise**|`git apply`||
|**Appliquer une remise spécifique non-nommée**|`git stash apply stash@{n}`|git stash apply stash@{0}|
|**Lister les remises**|`git stash list`||

&nbsp;

## Supplément(s)
### Annexe 1 - Réinitialisation 
#### &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; A. La commande `reset`
La commande `git reset` permet d'annuler des changements et peut être appelée de trois façons différentes, qui correspondent aux arguments de la ligne de commande **--soft**, **--mixed** et **--hard**.

![Types de réinitialisation](https://user.oc-static.com/upload/2019/07/02/15620712098159_09.jpg)
#### L'argument --hard
Permet de **revenir à n'importe quel commit** en oubliant **tout** ce qui a pu être modifié après.

Cette utilisation de `git reset` va constituer une manière simple d'annuler des changements qui n'ont pas encore été partagés.

&nbsp;

#### L'argument --mixed
Permet de revenir juste **après le dernier commit** **ou** le **commit spécifié** **sans annuler** les **modifications** en cours. Il va cependant créer un HEAD détaché (un HEAD est un pointeur vers la position actuelle sur laquelle on se trouve dans notre répertoire de travail. Par défaut, HEAD pointe sur la branche courante et peut être déplacé vers une autre branche ou un autre commit).

L'avantage est de pouvoir désindexé des fichiers non commités.

À noter que si rien n'est spécifié après la commande `git reset`, par défaut un `git reset --mixed HEAD~` sera exécuté.

&nbsp;

#### L'argument --soft

Le `git reset --soft` permet uniquement de se **placer** sur un **commit spécifique** afin de **voir le code** à un instant donné **ou créer une branche** partant d'un ancien commit. 

À contrario des deux arguments précédents, il ne supprime aucun fichier, aucun commit, et ne crée pas de HEAD détaché.

&nbsp;

#### &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; A. La commande `revert`
La commande `revert` permet de faire un *undo* (*i.e. un retour en arrière*) tout en préservant l'intégrité de l'historique. Et va en quelque sorte réaliser un *undo* en inversant l'action réaliser dans un nouveau *commit*.

La différence entre la commande `reset` et `revert` expliquée schématiquement : 

![Différence entre reset et revert](https://user.oc-static.com/upload/2019/07/02/15620714617275_10.jpg)

