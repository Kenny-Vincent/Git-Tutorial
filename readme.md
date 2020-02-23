# Tutoriel pour Git

---

## 1 - Installation

---

> _Première étape, télécharger et installer GIT avec le lien en dessous, c'est très simple et instinctif._

[Git - Page de Téléchargement](https://git-scm.com/downloads)

> _Suivez les instructions. Lorsque l'installation est terminée, ouvrez un terminal/invite de commande et commencez à écrire les instructions ci-dessous. (J'ai marqué 3 façons différentes d'ouvrir un terminal juste en dessous.)_
>
> - **\*'cmd'** dans l'executer de windows.\*
> - **\*Terminal** depuis le lunchpad pour les utilisateurs MacOS.\*
> - **\*Terminal->New Terminal** depuis le menu de VScode pour les utilisateurs de cet éditeur.\*

    $ git --version

> _Si votre terminal de commande répond ceci :_

    $ git version 2.22.0

> _L'installation est alors réussie, vous pouvez continuer votre route jusqu'à l'étape 2 ! (Si la version affichée n'est pas la même ce n'est pas grave.). Si vous ne voyez pas la ligne ci-dessus, il faut retenter l'installation ou se tourner vers la documentation pour résoudre le probème !_

---

## 2 - Initiate Git in a project

---

> _Nous allons voir comment initier Git dans un nouveau projet._
>
> - _Premièrement, nous devons créer un nouveau projet avec la commande :_

    $ mkdir PathToAFolder/MyAwesomeProject

> - _Il faut ensuite rentrer dans le fichier avec :_

    $ cd PathToAFolder/MyAwesomeProject/

> - _Maintenant, on va (enfin) initier Git, comme d'habitude, regardez ci-dessous._

    $ git init

> - _Il (le terminal ou l'invite de commande) va nous retourner ceci :_

    $ Initialized empty Git repository in PathToAFolder/MyAwesomeProject/.git/

> - _Maintenant, nous pouvons vérifier le statut de nos fichiers dans le répertoire, ce sera pratique plus tard, essayez maintenant avec :_

    $ git status

> - _Maintenant, vous pouvez voir quelques informations à propos de nos fichiers. Actuellement il n'y a rien dans notre fichier.. Donc cette instruction nous retourne presque rien ! (Nous verrons ce qu'est une branche et un commit après.)_

    On branch master
    No commits yet

---

## 3 - Qu'est qu'un commit ?

---

> _Pour la prochaine étape, j'ai créé un fichier HTML par défaut que j'ai placé dans notre projet. Vous pouvez faire de même ou bien placer vos propres fichiers qui viennent d'un de vos projets par exemple..._

![Imgur](https://i.imgur.com/ft0wJRX.png)

> _Si vous voulez copier mon fichier pour suivre ce tutoriel, copiez le code ci-dessous._

    <!DOCTYPE html>
    <html lang="en">

    <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Git Tutorial</title>
    </head>
    <body style="background-color: rgb(41, 123, 155); text-align: center;">
    <h1 style="margin-top: 20%; margin-bottom: 20%;">My Git Tutorial</h1>
    </body>
    </html>

> **Maintenant, nous allons apprendre ce qu'est un commit, et comment procède-t-on pour en créer un !**

> _Si vous voulez enregistrer l'avancée de votre projet, vous allez devoir demander à git de créer une sauvegarde de l'intégralité ou d'une partie de celui-ci. Pour faire ceci nous allons devoir créer ce fameux 'commit'._

> _Pour faire un commit, il faut procéder en deux étapes :_
>
> 1. Sélection le ou les fichiers que vous souhaitez sauvegarder.

    $ git add fileName

_(Par exemple : git add index.html)_

> 2. Créer la sauvegarde de vos fichiers selectionnés.

    $ git commit -m "My first commit"

_(Par exemple: git commit -m "Project Init")_

> _Nous avons créé une sauvegarde de notre projet (ou une partie tout du moins). Maintenant, nous allons éditer un de nos fichiers. Dans mon cas, je vais éditer la couleur du H1, elle passera du noir au blanc. (Vous pouvez copier ma modification ci-dessous.)_

    <!DOCTYPE html>
    <html lang="en">

    <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Git Tutorial</title>
    </head>
    <body style="background-color: rgb(41, 123, 155); text-align: center;">
    <h1 style="margin-top: 20%; margin-bottom: 20%; color: white;">My Git Tutorial</h1>
    </body>
    </html>

> _Quand la modification est terminée, vous pouvez ajouter le fichier modifier avec la commande **\$ git add filename** (Dans mon cas : **git add index.html**). Et après, il faut faire exactement pareil que précédemment, vous faîtes un **got commit -m "My edit"** (Pour moi : **git commit -m "h1 edit color"**)._

> _Vous avez donc deux commits désormais (J'espère !), On peut voir l'historique de ces commits avec :_

    $ git log

> _Et le terminal devrait vous retourner quelque chose comme ça._

    commit 53315cc5cbd8eaf38c4b04505565669e9beaae8e (HEAD -> master)
    Author: Kenny Vincent <kennyvincentpro@gmail.com>
    Date:   Tue Feb 18 16:34:15 2020 +0100

    h1 edit color

    commit bcc386a2de51a47b483f8043b54c360e6b40eaaf
    Author: Kenny Vincent <kennyvincentpro@gmail.com>
    Date:   Tue Feb 18 16:15:59 2020 +0100

    Project Init

> _Vous pouvez voir les deux commits que nous avons fait depuis le début du projet, le nom de l'auteur, la date et la description de nos commits._

---

## 4 - Une branche ?

---

> _Après les commits, les branches !_ > _On peut dire qu'une branche est une copie de notre projet initial ou on peut travailler sereinement parce que si vous n'appréciez pas ce que vous avez fait, vous pouvez supprimer la branche et au contraire, si le travail vous convient, vous pouvez fusionner votre branche à votre projet initial._

> _Pour créer une branche on utilise :_

    $ git branch MyBranch

_(Par exemple : git branch backgroundColor)_

> _Vous pouvez créer autant de branches que vous voulez, c'est pour ça qu'il est important de nommer nos branches en fonction de la fonctionnalité que vous allez créer dans la branche. Par exemple la branche 'Background color' de mon site internet. Comme vous l'avez peut-être deviné, la branche master est la branche initiale de notre projet. L'instruction en dessous peut vous montrer toutes les branches d'un projet._

    $ git branch

![Imgur](https://i.imgur.com/XzsjLEb.png)

> _Voys devriez voir quelque chose comme sur le screen ci-dessus._
> _Comme vous l'avez peut-être remarqué, la branche 'master' est écrite dans une couleur différente. C'est parce que nous sommes actuellement situé sur la branche master._

> _Si vous voulez travailler sur notre nouvelle branche, il faut commencer par changer de branche avec :_

    $ git checkout MyBranch

_(Par exemple : git branch backgroundColor)_

> _Git renverra alors :_

    Switched to branch 'MyBranch'

> _Maintenant, nous voulons changer la couleur de notre background. Vous pouvez copier mon code ci-dessous. (Ou éditer quelque chose sur l'un de vos fichiers.)_

    <!DOCTYPE html>
    <html lang="en">

    <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Git Tutorial</title>
    </head>
    <body style="background-color: #9b59b6; text-align: center;">
    <h1 style="margin-top: 20%; margin-bottom: 20%; color: white;">My Git Tutorial</h1>
    </body>
    </html>

> _Quand l'édit est complet, nous allons faire un commit de notre fichier édité sur notre nouvelle branche, vous comprenez maintenant surement ce que vous devez faire pour faire un commit, mais je remets les commandes en dessous si jamais vous êtes perdu !_

    $ git add filename
    $ git commit -m "MyEdit"

_(Par exemple:_<br>
_git add index.html_<br>
_git commit -m "Edit of my background" )_

> _Maintenant, ma fonction est terminée, je veux fusionner ma nouvelle fonction avec mon projet initial pour récupérer tout le contenu._

> _Pour faire ceci, trois étapes :_
>
> - _Se placer sur la branche qui va recevoir la nouvelle fonctionnalité. (La branche master dans notre cas.)_

    $ git checkout master

_Quand vous vous placez sur la branche master, vous pouvez voir que la modification de votre background-color n'existe plus. C'est dû au fait que nous ne sommes plus situé sur la même branche, donc plus sur la même sauvegarde de votre fichier._

> - _Nous allons demander à git de faire la fusion maintenant._

    $ git merge MyBranch

_(Par exemple : git merge backgroundColor)_

> - _Maintenant, vous pouvez faire un **\$ git log** pour voir si la fusion à bien fonctionnée. Vous allez voir votre dernier commit fait sur la branche backgroundColor sur votre branche master désormais._

> _La dernière étape n'est pas obligatoire, mais personnellement, je vous la recommande pour des soucis de gestion des branches._

    $ git branch -d Mybranch

_(Par exemple : git branch -d backgroundColor)_

> - _Vous pouvez voir que votre branche backgroundColor a été supprimée, et vous pouvez donc vérifier ça avec **\$ git branch**._

---

**\_Si vous lisez ceci et que vous avez suivi les étapes ci-dessus, bravo, vous savez comment utiliser git localement ! Nous allons voir dans les étapes en dessous comment utiliser git en collaboration grâce à des dépôts distants !**

---

## 5 - GitHub

---

> - _Github est un outil qui va nous permettre de créer des dépôts distants où nous pourrons placer nos commits et nos branches afin de sauvegarder l'avancée de nos projets. En utilisant un dépôt distant, il sera possible de collaborer avec d'autres personnes sur le même projet !_

> - _La première étape et de ce créer un compte :_

[Github](https://github.com/)

> - _Je vous laisse cette étape. Elle n'est pas compliquée et il n'y a aucun piège !_

> - _Une fois terminé, créé un nouveau dépôt (Vous pouvez voir à quoi cela ressemble en-dessous)._

![Imgur](https://i.imgur.com/x4oC6DE.png)

> - _Maintenant, nous devons connecter notre dépôt local et notre dépôt distant pour pouvoir sauvegarder nos fichiers en ligne directement depuis notre ordinateur. Github nous donne exactement les commandes à faire ensuite pour lier nos dépôts._

![Imgur](https://i.imgur.com/8gylVIW.png)

> - _Vérifiez si tout a bien fonctionné avec :_

    $ git remote

> - _Vous devriez voir maintenant 'origin', c'est votre dépôt distant !_

> - _Maintenant, vous pouvez envoyer tous vos fichiers sur github avec la seconde instruction donnée par github._

    $ git push -u origin master

> - _Et voilà ! Vous en savez désormais beaucoup plus sur Github ! Pour travailler à plusieurs sur un projet, il suffira de donner l'accès de vos projets à d'autres développeurs inscrits sur Github et le tour est joué !_
