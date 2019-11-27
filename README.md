# GitHub Tutorial

_by Wilmer Uguna_

---
## Git vs. GitHub

> To begin we need to know what Git and Github are.
In a short explanation, Git and Github manage your code and allows you to keep track of different versions.

* **Git**
    * Version control: Keep “snapshots” (record) of your code
        * Can easily revert one specific   command
        * Keep a timeline of your code
    * Most importantly it does not require Github

* **Github**
    * It stores your code in the cloud
    * You can visually track changes
    * Makes it easy to collaborate on files
    * Requires Git

---
## Initial Setup

**Setup your Github:**
* To first have a github account go to  [Github.com](https://github.com/)
    * Click sign-up (If you're an hstat student use your hstat email to sign up and your osis number as your password)
> Github is where all your repositories in the cloud will be located. Here you can access it, see the changes and even create other repositories if you want
* Congratulations you now have a GitHub account!!!!

**Setting up your user info:**
1. Go to [ide.cs50.io](http://ide.cs50.io/)
2. If you haven't already done so click sign in or else skip this step
3. In your command line type `git config --global user.email "you@example.com"`  
    A. **DO NOT COPY AND PASTE BECAUSE YOU NEED YOUR OWN EMAIL**  
    B.  Don't forget the quotes
4. Then type ``git config --global user.name "Your Name"``

 **Generating and connecting an SSH key:**
> An SSH allows you to upload your local (ide) to the remote (GitHub) without the necessity of having to sign in every time.

*  Make sure that you're in your root directory. If you're not type `cd~` into your command line
* In the command line type `ssh-keygen -t rsa -b 4096 -C "you@example.com"`
    * Press enter *slowly* until you see:
```
* The key's randomart image is:

+--[ RSA 4096]----+
|       .o o..    |
|       o +Eo     |
|        + .      |
|         . + o   |
|        S o = * o|
|           . o @.|
|            . = o|
|           . o   |
|            o.   |
+-----------------+
```
* `eval "$(ssh-agent -s)"` starts the agent in the background
* `ls -al ~/.ssh` you should now see a file named id_rsa.pub
* `cat ~/.ssh/id_rsa.pub ` then copy all of the result to your clipboard (it should start with ssh-rsa and end with your email address)

* Go to https://github.com/settings/keys
    * Title: ide50
    * Key: paste your ssh key
    * Press the green Add SSH key button
* Back in your ide type `sudo nano ~/.ssh/config`
* Paste the following:
``` 
Host github.com 
Hostname ssh.github.com 
Port 443 
```  
* `control+X ` to exit, then press `Y` then `ENTER`
* `ssh -T git@github.com`
* Type `yes`, press `ENTER`, and you should see
>Hi "username"! You've successfully authenticated, but GitHub does not provide shell access.
* Congratulations you are done connecting your ide with GitHub and the SSH key. You can now upload your repositories to the remote (Github) without having the need to sign in every time. 
---
## Repository Setup

> A repository is a folder that you have git runnning in. This repository would be uploaded to the remote. Keep in mind all repositories are directories but not all directories are repositories. You may be wondering how would I make a repository then. Well follow the steps bellow to setup it up.

There are two ways to make a repository via your ide or the Github.com site. 

* First lets learn how to do it straight off of your ide.
    * In the command line type `git init` for the directory you desire to turn into a directory 
        * **REMEMBER TO** `cd <filename>`
        * You should now see in your command line (master). If you see this it means git is now active in the repository.
    * Now you have to make a README.md file in the repository.       
        * In the command line type `touch README.md`  
        
    * In this newly made file you can type anything you want and save it. This is where our two other commands `git add .` and `git commit -m "specific/short message`

---
## Workflow & Commands

`git init` - Initializes git in our directory (now we call it repository) for version control - only do this in the beginning.
* While using `git init` keep in mind:
    * To do it in the directory you want to turn into a repository
    * **_NEVER TO DO IT IN ROOT DIRECTORY_**


`git status`  -  Optional command to see what files have been edited since the last commit.

`git add`  -  adds any changes made in file to the stage to be committed.
* This command could be used in various ways. You could choose what you want to add to the stage and what you don't want to add in the stage.
    * `git add <file.ext>`  -  add the file(s) to the stage to be committed
    * `git add .`  -  adds all files that have changes


`git commit`  -  take a ‘snapshot’ of the files on the stage.  The message should be present-tense and describe what was modified in this snapshot.

`git log` -  Allows you to see your past commits
* Press Q to quit

---
## Rolling Back Changes