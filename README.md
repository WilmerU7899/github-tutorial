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

1. Go to [Github.com](https://github.com/)  
    a.  Click sign-up (If you're an hstat student use your hstat email to sign up and your osis number as your password)


---
## Repository Setup



---
## Workflow & Commands

`git init` - Initializes git in our directory (now we call it repository) for version control - only do this in the beginning.  
* While using `git init` keep in mind:
    * To do it in the directory you want to turn into repository 
    * **_NEVER TO DO IT IN ROOT DIRECTORY_**


`git status`  -  Optional command to see what files have been edited sicne the last commit.

`git add`  -  adds any changes made in file to the stage to be committed.  
* This command could be used in variuos ways. You could choose what you want to add to the stage and what you don't want to add in the stage.
    * `git add <file.ext>`  -  add the file(s) to the stage to be committed  
    * `git add .`  -  adds all files that have changes  
    

`git commmit`  -  take a ‘snapshot’ of the files on the stage.  The message should be present-tense and describe what was modified in this snapshot.  

`git log` -  Allows you to see your past commits
* Press Q to quit 

---
## Rolling Back Changes