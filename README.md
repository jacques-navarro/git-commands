7# git-commands
git cheat sheet

## Getting a repository

**git init* initializes a repository

**git clone** <url> [directory] clones a repository

##Getting info

**git status** displays current branch, untracked files, modified files, added files

**git diff** displays what has been modified but not staged
--staged displays the what has been staged compared to the last commit

**git log** lists commits in reverse chronological order
-p (patch) shows difference introduced by each commit
-<n> shows last nth commits

##Making changes

**git add** <file> stages new files and tracked files that have been modified

**git commit** commits any  changes that have been staged. Launches editor for commit message
-m accepts inline commit message
-a skips staging area and commits any tracked files that have been modified
--ammend undoes last commit and returns to staging

**git rm** remove files that are currently been track

**git mv <original file> <renamed file>** move/rename a file or rename

##Undoing things

**git reset HEAD** <file> unstage files

**git checkout** -- <file> discard files which are not staged

##Working with remotes

**git remote** displays which remote servers have been configured
-v displays URLs stored in git for fetching and pulling
add <short name> <URL> adds new remote repository with specified short name
show <short name> displays URL and branch information

**git fetch** <short name>[/branch name] pulls down all data that you don't have yet from a remote repo
pull downloads and merges remote into current code

**git push** <short name> <branch name> only works if another commit hasn't been pushed to remote

##Working with branches

**git branch** <branch name> - creates a new branch
-d <branch name> - delete branch

**git checkout** <branch name> - switch to an existing branch
-b <branch name> - create a new branch and switch to it automatically

##Merging
Switch to branch you would like to merge changes into. **git checkout** <branch name>

**git merge** <branch name> merge branch into current branch
