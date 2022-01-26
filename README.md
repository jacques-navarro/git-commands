# git-commands
git cheat sheet

## Getting a repository

`git init` initializes a repository

`git clone <url> [directory]` clones a repository

## Getting info

`git status` displays current branch, untracked files, modified files, added files

`git diff` displays what has been modified but not staged  
`--staged` displays the what has been staged compared to the last commit

`git log` lists commits in reverse chronological order  
`-p` (patch) shows difference introduced by each commit  
`-<n>` shows last nth commits  

## Making changes

`git add <file>` stages new files and tracked files that have been modified

`git commit` commits any  changes that have been staged. Launches editor for commit message  
`-m` accepts inline commit message  
`-a` skips staging area and commits any tracked files that have been modified  
`--ammend` undoes last commit and returns to staging  

`git rm` remove files that are currently been track

`git mv <original file> <renamed file>` move/rename a file or rename

## Undoing things

`git reset HEAD <file>` unstage files

`git checkout -- <file>` discard files which are not staged

## Working with remotes

`git remote` displays which remote servers have been configured  
`-v` displays URLs stored in git for fetching and pulling  
`add <short name> <URL>` adds new remote repository with specified short name  
`show <short name>` displays URL and branch information  

`git fetch <short name>/[branch name]` pulls down all data that you don't have yet from a remote repo  
`pull` downloads and merges remote into current code

`git push [short name] [branch name]` only works if another commit hasn't been pushed to remote

## Working with branches

`git branch` - lists all branches
`git <branch>` - creates a new branch  
`-d <branch>` - delete branch which has been merged  
`-D <branch> - delete branch that has not been merged  
`-v` display last commit on each branch  
`--merged` display only branches which have been merged into current branch  
`--no-merged` display only branches which have not been merged into the current branch  
`--move <old branch name> <new branch name>` rename branch (must use `git push --set-upstream origin <new branch name>` to set up branch on remote and `git push origin --delete <old branch name>` to delete old branch on remote)  
`-m <old name> <new name>` - rename branch

`git checkout <branch | sha1>` - switch to an existing branch | commit  

`git switch -c <branch name>` - create a new branch and switch to it automatically     

## Merging
Switch to branch you would like to merge changes into. `git checkout <branch name>`

`git merge <branch name>` merge branch into current branch  

## First time setup

`git config --list --show-origin` view all settings    
`--global user.name <user name>` set user name    
`--global user.email <user email>` set user email address    
`--global core.editor <text editor name>` set default text editor    
`<setting>` check setting    


## Getting help
`git help <verb>` 


## Connecting to Github with SSH

* [Checking for existing SSH keys](https://docs.github.com/en/free-pro-team@latest/github/authenticating-to-github/checking-for-existing-ssh-keys)  
  * [Generating a new SSH key and adding it to the ssh-agent](https://docs.github.com/en/free-pro-team@latest/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)  
* [Adding a new SSH key to your GitHub account](https://docs.github.com/en/free-pro-team@latest/github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account)  
  * use `cat ~/.ssh/<ssh public key file>` to copy ssh public key  
* [Testing your SSH connection](https://docs.github.com/en/free-pro-team@latest/github/authenticating-to-github/testing-your-ssh-connection)  
