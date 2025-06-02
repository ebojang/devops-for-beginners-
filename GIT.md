Git is a distributed version control system used to track changes in source code during software development. 
**why?**
it allows multiple developers to work on the same project without conflicting and enable the tracking of every single change.
once completed, branch feature or dev branches merge into main branch (production).
if production version 2 breaks, you can always roll back to version1.


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

