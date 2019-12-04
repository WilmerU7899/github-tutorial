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
    * For your username you could use the beginning part of the email you put. So it should be like `firstname_lastname_last4osis#`
> Github is where all your repositories in the cloud will be located. Here you can access it, see the changes and even create other repositories if you want
* Congratulations you now have a GitHub account!!!!

**Setting up your user info:**
> Follow the steps in the link below to setup your github with your ide.

[github.com/hstatsep/ide50](https://github.com/hstatsep/ide50)

---
## Repository Setup

> A repository is a folder that you have git runnning in. This repository would be uploaded to the remote. Keep in mind all repositories are directories but not all directories are repositories. You may be wondering how would I make a repository then. Well follow the steps below to setup it up.


* Lets learn how to do it straight off of your ide.
    * In the command line type `git init` for the directory you desire to turn into a repository
        * **REMEMBER TO** `cd <filename>`
        * You should now see in your command line (master). If you see this it means git is now active in the repository.
    * Now you have to make a README.md file in the repository.
        * In the command line type `touch README.md`
            * In a "README.md file" instructions/description of the project gets presented.

    * In this newly made file you can type anything you want and save it. This is where our three other commands: `git add .` `git status` & `git commit -m "specific/short message`
        * Type anything in the README.md file
        * Now go back to your command line and type `git status`
            * It should say "modified: README.md" in red
            * In short terms this is just the computer telling you that there was some change in the file.
        * After this in the command line type `git add .`
            * If you type `git status` after `git add .` it should say "modified: README.md" in green
            * All it means is that you have added it to the stage and you can now commit it (save it).
        * If green you can type in the command line `git commit -m "specific/short message"`
            * Keep in mind this specific message describes the changes you made in the file.
            * It also has to be short and in the present tense.

>After `git commit` it will save and now you can go make more changes. After any change you should always do `git add .` & `git commit` to keep track of your changes.


---
## Workflow & Commands
> You just used a lot of commands but you dont know what exactly they do. Well right below this is an explanation of each command you already used or may use in the future.

`git init` - Initializes git in our directory (now we call it repository) for version control - only do this in the beginning.
* While using `git init` keep in mind:
    * To do it in the directory you want to turn into a repository
    * **_NEVER TO DO IT IN ROOT DIRECTORY_**

`git status`  -  A command that lets you see what files have been edited since the last commit. The ide will show you the color green if edits have been added ready to commit. On the other hand, if you haven't added the edits to the stage it will show up in red.

`git add`  -  Adds any changes made in file to the stage to be committed.
* This command could be used in various ways. You could choose what you want to add to the stage and what you don't want to add in the stage.
    * `git add <file.ext>`  -  Add a specefic file(s) to the stage to be committed (saved)
    * `git add .`  -  adds all files that have changes in them

`git commit -m "specific/short message`  -  Take a ‘snapshot’ of the files on the stage. In other words this is like a save feature.  The message should be present-tense and describe what was modified in this snapshot. Use it after you added the file(s) to the stage

> If you ever want to see the different commands youve done in the pasts the followingg two commands will help you.

`git diff`  -  It check what changes made between the two last commits.

`git log` -  Allows you to see your past commits
* Press Q to quit

#### Pushing and Pulling
> Once you want to push your commits from your local repo to your remote repo or vice versa the following commands will work. Keep in mind in other to use `git push` you will have to do some extra steps before putting it in use . Under these 3 commands, there will be instructions on how to begin using `git push`

`git push` -  Sends any changes from local repo “up” to the remote repo
* Should be used constantly after each commit to have a back up of it

###### Push

1. Go to your local ide. (https://ide.cs50.io/)
    * Sign in if you need to do so
2. Now the remember the name of the repository you want to push
    * This repository must have a file already named "README.md"
    * This will be **very** important later on
3. Go to [github.com](https://github.com)
4. Click on the plus icon
5. Click on New Repository
6. Enter the name of your repository from your ide
    * This has to be identical or else it wont work
7. Scroll down and make sure you have "Initialize this repository with a README" **OFF**.
8. Click the green button _"Create Repository"_
    * This will direct you to another page
9. You will see code similar to this
    * If you dont, make sure SSH key is turned on instead of HTTPS

```
git remote add origin git@github.com:user_name/repository_name.git
git push -u origin master
```
10. Copy the code from **YOUR** page and paste it in the command line
11. Press enter

> In simple words what you just did is set the location of where the ide is going to push. Now whenever you `git push` you the location set. If you ever want to know where exactly you're pushing or pulling type this command below:

`git remote -v` - Tells you where git push or git pull will send your commits

> On the other hand `git pull` you can use right away. It doesn't require long steps and a procedure to use.

`git pull` - Bring any changes from the remote repo “down” to the local repo
* Should use if you worked on the remote repo instead of the local

---
## Rolling Back Changes

> Everyone makes mistakes but its important to know how to undo what you do.

* If you ever do `git init` in a directory you didnt want to, tpye:
    * `rm -rf .git`
        * This will unitialize git

> That right there is a simple mistake but you also may edit, add and commit and then later change your mind about it. Its important to know how to undo each one of them individually.

* If you ever want to undo an edit of file type:
    * `git checkout -- file`
    * This could come into use if you want to undo every single change you did in the file.
    * Keep in mind this will only work if you havent added it yet.

* If you ever want to undo what you added type:
    * `git reset HEAD file`
    * This could come into use if you added the change to the stage and now have changed your mind

* If you ever want to undo a commit type:
    * `git reset --soft HEAD file`

* If you ever want to undo both a commit and what you added tpye:
    * `git reset HEAD~1`
    * Keep in mind this will send you to the editing stage and undo both what you added and commited

> You may be wondering is there a way to undo everything. Well indeed there is a way.

* If you ever want to undo the edit, what you added and the commit type:
    * `git reset --hard HEAD file`
    * This will take you all the way to the beginning even before any edits.

* If you ever want to "Unpush" tpye:
    * `git reset --hard [first nine digit of SHA]`
    * This command erases the commit you made from your remote.
