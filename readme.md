# Tutorial for Git

---

## 1 - Installation

---

> _First step, download and install GIT with the link bellow, It's very simple and instinctive._

[Git - Downloads](https://git-scm.com/downloads)

> _Follow the intructions. When it's done, open an Terminal and write the instruction bellow. (You can see how open a terminal just bellow)_
>
> - **\*'cmd'** in executer for Windows users.\*
> - **\*Terminal** from the lunchpad for MacOS users.\*
> - **\*Terminal->New Terminal** from the menu of VScode for VScode users.\*

    $ git --version

> _If you can see this line bellow :_

    $ git version 2.22.0

> _The installation is complete, you can keep your road to the second step ! (Even if the version is not the same)._ > _If you don't see the line, you have to download GIT again and try to re-install it._

---

## 2 - Configure your user profile

---

> _Write both lines bellow. It will set your git profile on your computer. It will allow you to use git without have to login every time you want to do a thing._

    $ git config --global user.name "Kenny Vincent"
    $ git config --global user.email "example@gmail.com"

---

## 3 - Initiate Git in a project

---

> _We will see how to init Git in a new project._
>
> - _First, we have to create a new project with :_

    $ mkdir PathToAFolder/MyAwesomeProject

> - _You have to enter in the file now._

    $ cd PathToAFolder/MyAwesomeProject/

> - _Now we will (finally) init Git, write the line bellow._

    $ git init

> - _It will return this :_

    $ Initialized empty Git repository in PathToAFolder/MyAwesomeProject/.git/

> - _Now we are allowed to check the status of our files in the folder, it will be useful later, try it now with :_

    $ git status

> - _Now you can see some informations about the files in your folder. Actually there is nothing in your folder, so this instruction return you almost nothing (We will see what is a 'branch' and a 'commit' after)_

    On branch master
    No commits yet

---

## 3 - What is a commit ?

---

> _For the next step, I have create a random HTML file, you can do the same, or you can put your own files from one of your project._

![Imgur](https://i.imgur.com/ft0wJRX.png)

> _If you want to copy my file just to follow the step of this tutorial, copy the code bellow._

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

> **So, we will learn what a commit is, and how procede to make one.**

> _If you want to register the advanced of your project, you will have to ask git to create a save of the integrality or a part of your project. To do that you have to make a 'commit'._

> _To make a commit, it work in **2 steps** :_
>
> 1. Select the files you want to save.

    $ git add fileName

_(By example : git add index.html)_

> 2. Create the save of your selected files.

    $ git commit -m "My first commit"

_(By exemple : git commit -m "Project Init")_

> _We have create a save of your project (or a part of your project). Now, let's edit one of your files. In my case, I will edit the h1 color text, passing from black to white (If you want, you can copy my edit bellow)._

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

> _When the edit is done, you can add your project with **\$ git add filename** (In my case I have to do : **git add index.html**). And after, we do the same as before, you do a **\$ git commit -m "My Edit"** (For me : **git commit -m "h1 edit color"**)._

> _You have done now 2 commits (I hope !), We can now see the timeline of our commits with :_

    $ git log

> _And the terminal should return something like this._

    commit 53315cc5cbd8eaf38c4b04505565669e9beaae8e (HEAD -> master)
    Author: Kenny Vincent <kennyvincentpro@gmail.com>
    Date:   Tue Feb 18 16:34:15 2020 +0100

    h1 edit color

    commit bcc386a2de51a47b483f8043b54c360e6b40eaaf
    Author: Kenny Vincent <kennyvincentpro@gmail.com>
    Date:   Tue Feb 18 16:15:59 2020 +0100

    Project Init

> _You can see both commits we've done since the start of the project, the name of the author, the date and the explanation of the commit._

---

## 4 - What is a branch ?

---

> _After the commit, the branch !_ > _We could say that a branch is an copy of your initial project where you can work serenely because if you don't like what you've done, you can delete the branch and if the work done on the branch suits you, you can merge it on the initial branch of your project._

> _To create a branch, we use :_

    $ git branch MyBranch

_(By example : git branch backgroundColor)_

> _We can create how many branch as we want, that's why it's important to named the branch depending of the functionality you will create in the branch. By example the backgroundColor branch is use to change the background color of my website. By the way, the branch master is the initial branch of our project. The instruction bellow can show you all the branchs of an project_

    $ git branch

![Imgur](https://i.imgur.com/XzsjLEb.png)

> _You should see something like the screen above._ > _As you maybe notice it, the branch 'master' is write in a different color and with an asterisk. It's because you are situated in the branch master currently._

> _If you want to work in our new branch, you have start by changing the current branch you work in with :_

    $ git checkout MyBranch

_(By example : git branch backgroundColor)_

> _And it should return :_

    Switched to branch 'MyBranch'

> _Now, we want to change the color of our background. You can copy my code bellow (or edit something on one of your file)._

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

> _When the edit is complete, we will do a commit of our edited file on our new branch, you probably started to understand what you have to do for a commit, but I put the commands bellow if you ae lost._

    $ git add filename
    $ git commit -m "MyEdit"

_(By example :_<br>
_git add index.html_<br>
_git commit -m "Edit of my background" )_

> _You can after, write a **\$ git log** to see what is about your previous commit on your new branch._

> _Now, my function is done, I want to merge my new function with my initial project to recover all the content._

> _To do that, you have to procede in 3 steps :_
>
> - _Place yourself in the branch that will receive the new functionality. (So the Master branch in our case.)_

    $ git checkout master

_When you checkout on the master branch, You can see the modification of your background-color is back to the same color have you set in first time. It's because your not using the same save of your file now, you are using the save done on your master branch, and not anymore the last commit you did on the backgroundColor branch._

> - _We will ask git to merge the branch now._

    $ git merge MyBranch

_(By example : git merge backgroundColor)_

> - _Now, you can do a **\$ git log** to see if the merge had work well. You should see your last commit did on backgroundColor branch, on your master branch now._

> _the last step is not necessarily required, but personally, I advise you to do this step for organizational concerns.._

    $ git branch -d Mybranch

_(By example : git branch -d backgroundColor)_

> - _You can see that your branch have been delete, you can verify with a **\$ git branch**._

---

**_If you read this and if you have done all the thing above, congratulation, you know how to use git locally ! We will see in the steps bellow how to use git in collaboration thanks to remote repositories._**

---

## 5 - GitHub

---

> - _Github is a tool that will allow us to create remote repositories where we can place our commits and the progress of our projects. By using remote repositories, it will be possible to collaborate with other people on the same project !_

> - _The first step is to create an account on :_

[Github](https://github.com/)

> - _I leave you this step. It's not hard and there is no trap !_

> - _When your account creation is done, create a new repository (you can see what it's look below)._

![Imgur](https://i.imgur.com/x4oC6DE.png)

> - _Now, we have to connect our local repository and our remote repository to be able to save our files online directly from our computer. Github give you exactly what you have to do to link your repositories._

![Imgur](https://i.imgur.com/8gylVIW.png)

> - _You can check if the link is working with :_

    $ git remote

> - _You should see now 'origin'._

> - _Now you can send all your files on github with the second instruction gived by github._

    $ git push -u origin master
