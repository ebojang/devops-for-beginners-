
GIT: is a software 
Github: is a service provider . example when you work on a git and wants to save it on the cloud, that's when github is used.


Git is a distributed version control system used to track changes in source code during software development. 


**WHAT IS VERSION CONTROL?**
Version control tracks changes in source code/ files during software development. it helps undo, inspect and collaborate. 
it helps revert if anything goes wrong. 


**why?**
it allows multiple developers to work on the same project without conflicting and enable the tracking of every single change.
once completed, branch feature or dev branches merge into main branch (production).
if production version 2 breaks, you can always roll back to version1.

note 
Git is not just a file tracker. Git tracks snapshots and not diffs. it takes snapshots of what the file looks like at that point in time. 
Git uses a key value store (SHA-1 Hash).
no two different blobs or objects will have the same hash.
git is content-addressed, not file-name based. this means if the file changes, the hash changes. 

**GIT INTERNALS AND CORE CONCEPTS** 
 **REPO-** is a folder which contains lots of software files
 git --version or git -v 
check git status by running 
git status - check git status 

 **==How to track a particular folder in your repo?

**Working Dir > git add > Staging Area > git commit > Repo > Git push > Github** 
1)  first initialise the software: **git init
 git init is run one time per project. **
 git initialised creates a .git folder. once run. 
 .git is a hidden folder that keep history of all files and sub folders
cd into your folder and run : ls -la (.git folder should now be created)
cd .git 
ls 
note
DO NOT GO INTO THE .GIT FOLDER TO CHANGE THINGS MANUALLY 

within your dir. create a working directory example mkdir gitone
cd gitone > touch test.txt test.txt 
run git status. . 
 # use "git add <filename> ...."  to keep the files under the tracking zone. 
example
git add testone.txt
git status: this should now show "changes to be committed: (filename to be tracked)"
note 
git add . (.) means add everything that I have 
now we are in the **staging area.  this is an intermediate zone before we make any commit.


 1) COMMIT is like a checkpoint.
 run
git commit -m (-m stands for message) "add file one"
 you can run **git log** - this gives you details of all the changes 
or **git --oneline** 
note :
a commit is always dependent on a previous commit. this helps us to track changes.
every time a commit is made, a hash is created  

****GIT CONFIGURATION FILE**** 

set git username :
git config --global user.name "Mona Lisa"
git config --global user.email "ebojang"

GIT IGNORE 

Gitignore is read by GIT itself. first create the file 
 touch .ignore
 once created, run git status
  open the .gitignore folder in vsc and insert the files and folders you don't want Git to track 







![[Pasted image 20250630211322.png]]

IF a folder have a .git directory inside, it is a **repo 

==**THE .GIT DIRECTORY**==
The .git folder is a hidden folder and every repo have a .git folder. 
.git is the brain of your projects. it contains all history and configs git needs to function. 

**.git/refs/** is the place where git stores all the branches and tags
**.git/objects/** is where git stores all commits, blobs and trees.
**.git/config** is where repo-specific settings are.
**.git/HEAD tells git what branch or commit you are currently on
.git/index is a staging area . this is a temporary zone 



**How do you branch out from the main branch in a GIT to dev branch and feature branch?


**Things to use everyday in git ?**

1) **git branch** (branch name have to be unique eg could be ticket ref-increase RDS size)
2) **git checkout** (ref-increase RDS size) -  this moves you from the main branch to dev or feature branch 
MADE CHANGES AND THEN CONTINUE THE STEPS BELOW 
3) **Git add** (your file path)
4) **Git commit -m****  (commit message) . the commit messages are the reason you are making changes eg to stop failing of RDS instances   
NOTE: Git commit message is a complete unit of work 
5) **Git push** this pushes it back to main branch 
note: before pushing to main branch/merging, a merge request or pull request is done as a checklist. A second pair of eye is needed before pushing to main/production branch
6) Git pull -  updates local computer and create a version 2 on main production.

**what is a merge conflict?**
merge conflict is a conflict between 2 pulls. 

[^1]: create a working directory> git add> Staging area> git commit>Repo>git push>Github


**GIT BRANCHES** 

Branches on git are like a timeline. branch name have to be unique eg could be ticket ref-increase RDS size)

HOW TO CREATE MULTIPLE BRANCHES IN GIT

git branch (branch name)
enter git branch (the new branch should now be under the master branch)

**TO SWITCH TO NEW BRANCH
git checkout/switch (new branch name)
git log --oneline
the head now points at the new branch . example 
master 
*testbranch

NOTE 
Head always points to where the branch is currently at