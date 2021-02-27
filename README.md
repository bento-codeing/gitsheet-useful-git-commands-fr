# Aides aux commandes Git

Voici une feuilles récapitulatives des différentes commandes Git les plus utiles et les plus utilisées.

|Description|Méthode|Exemple|
|-|-|-|
|Initialiser un *repository*|`git init`|
|Permet de pointer le dépot local au dépot distant|`git remote add [nom pour appeler le repo] [URL]`|git remote add OC https://github.com/OpenClassrooms-Student-Center/ProjetOpenSource.git|
|Cloner un *repository*|`git clone [HTTPS/SSH endpoint]`|git clone https://github.com/OpenClassrooms-Student-Center/ProjetOpenSource.git|
|Lister les branches. L'étoile (symbole : *) qui se situe près du nom d'une branche signifie la branche sur laquelle on se situe|`git branch`||
|Créer une branche|`git branch [nom de notre branche]`|git branch test|
|Basculer sur une branche|`git checkout [nom de notre branche]`|git checkout test|
|Créer une branche et basculer dessus|`git checkout -b [nom de notre branche]`|git checkout -b test2|
|Supprimer une branche|`git branch -d [nom de notre branche]`|git branch -d test2|
|Forcer la suppression d'une branche (i.e. avec des modifications dessus)|`git branch -D [nom de notre branche]`||
|Stager des modifications avant de les ajouter au *repository*|`git add [les fichiers que je souhaite stager/indexer]`|git add src/config/config.yaml|
|Archiver des modifications|`git commit`||
|Archiver des modifications avec un message|`git commit -m <string>`|git commit -m "Mon super message"|
|Afficher toutes les actions et leurs *SHA* dans l'historique *Git*| `git reflog`||
|Afficher l'état de nos fichiers, i.e. où se situe nos fichiers dans les 3 zones loacales majeures (Working Directory, Stage ou Repository)|`git status`||
