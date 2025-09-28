
GIT: is a software 
Github: is a service provider that host git online. example when you work on a git and wants to save it on the cloud, that's when github is used.


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

**GIT IGNORE** 

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

git commit -am (is another shortcut for adding and committing at the same time)
****GIT BRANCHES**** 

Branches on git are like a timeline. branch name have to be unique eg could be ticket ref-increase RDS size)

HOW TO CREATE MULTIPLE BRANCHES IN GIT

git branch (branch name)
enter git branch (the new branch should now be under the master branch)

TO SWITCH TO NEW BRANCH
git checkout/switch (new branch name)
git log --oneline
the head now points at the new branch . example 
master 
*testbranch

to create a new branch and move there, you can run 
git switch -c (new branch name)

NOTE 
Head always points to where the branch is currently at
always commit before switching to another branch

MERGING BRANCHES

There are two types of merging branches 
fast forward and not fast forward merge 

Fast forward merge

steps 
first check which branch you on 
git branch 
your branch should be pointed at master or the branch you are merging the new branch to 

git merge (dev branch name / secondary branch name)

DELETE GIT BRANCH 
git branch -d (branch name)


GIT COMMAND

git diff ( shows difference between the same file. )
it show you file state before stage (before commit) and after stage (after commit).

edit file 
run git status 
git add (filename)
git diff --staged ( this shows you the file before commit and current stage)

once run,
you will see
--- testfile.txt (this represents before staging)
++= testfile.txt (during staging)

GIT STASH 
git stash is like a temporary shelf/storage  where you can keep your code 
note:
conflicting changes do not allow to switch branch without commit 
error code 
error: Your local changes to the following files would be overwritten by checkout:**
        **heroeb.html**
        **test_branch.html**
Please commit your changes or stash them before you switch branches.**
Aborting

GIT stash is then use to move between branches.
 command git stash list- view all stashes 
once you complete switching branches and one to continue working on the branch you were on. 

git switch (branch you need to complete work on example ebranch)
git stash pop 
also you can run  git stash list 

git checkout HEAD ~2 (this looks at two commits prior)

git restore filename (file can only be restored back to the last commit only)

git reflog (takes you back to where you were )

git log --oneline --graph -all  - this gives you the full view. this is great for debugging merges and tracking branches. it helps you see what is really happening under the hood.


GIT REBASE 

Git rebase can be use as am alternative to merge or 
it can also be used as a clean-up tool (clean up commits)

NOTE
NEVER RUN GIT REBASE ON A MAIN/MASTER BRANCH. ONLY RUN ON A SIDE BRANCH

First check which branch you are on. 
example secondary branch 

git rebase master/main 

GITHUB 

Github - is a service to host git online.
it's a collaboration tool, it is used for backup and open source

REBASE VS MERGE 
* Merge brings two branches together and preserve the history. where as rebase rewrites history 
* merge creates a new commit where as rebase does not 
* merge is good for team work where as rebase is good for cleanup before production.
NOTE
DO NOT REBASE SHARE BRANCHES AS THIS SOMETIMES BREAK CODE AND CONFUSSION



GIT Cherry pick 

git cherry-pick allows you to apply a single commit from another branch to your current location.

git cherry-pick (commit one line ID of the commit you copied from another branch example 57a34bc)
git push 
 the copied commit ID  is now pushed into main or master branch.

FORKS & PULL REQUESTS

Fork= your own copy of someone else's repo (on Github)
clone the fork repo to your local machine  and make changes.
when changes are completed, push to your fork on Github. 
Open a pull request (PR) or megre to propose changes to the main project.

this is normally used in open source and cross team workflows.
once a PR is sent, orginal repo owner can review, comment and merge.


To UNDO A STAGED STATUS :
git restore --staged (filename)
git status 

to undo a commit message that has not been pushed yet, run
git reset --soft HEAD~1
This keeps your changes in staging 

VIEWING HISTORY 
git log: shows fullcommit history
git log --oneline --graph : shows clean visual summary layout
git show <commit> : helps view a specific commit 
git diff: compare unstaged changes with the last commit 
git diff --staged :compares your staged changes with the last commit
git blame <file>: shows who last changed each line 












