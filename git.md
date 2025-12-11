# git
Using Git: from https://phoenixnap.com/kb/how-to-use-git
sudo git init [reposiory name] //creates a local repository in the current directory
sudo git remote add origin https://github.com/zacherywalter/crispy-train.git //the origin of the local     repository can be set to a repository on github
git add train-list.txt //add a file to be tracked
git reset train-list.txt //remove a file from file-tracking (unstaging)
git status //tells you which files are being tracked/staged
git commit //to commit the staged files to your local repository

git branch //to list the branches
git branch [new branch name] / git checkout -b <new branch name> //to create a new branch
git branch -m <new name> //to rename a branch
git branch -d [branch name] //delte a branch
git checkout <branch name> //to switch to an existing branch

git log //to see a list of the different branches

Alternative way of switching branches
git switch <existing_branch>
git switch -c <non_existing_branch>

For example, to view the version of file <repository-root>/src/main.c from 4 commits ago, use:
git show HEAD~4:src/main.c

Using git stash, and some weird edge case.
https://stackoverflow.com/questions/22082307/git-switch-branch-without-discarding-local-changes
