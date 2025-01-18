![](git-hg.png)

## Getting a repository

`git init` initializes a repository

`git clone <url> [directory]` clones a repository into the current directory

## First time setup

`git config --list --show-origin` view all settings  
`--global user.name "<user name>"` set user name  
`--global user.email "<user email>"` set user email address  
`--global core.editor "<text editor name>"` set default text editor  
`[level] <option>` check setting  
`[level] --unset <option>`  
`-e` edit local config file

`git config --global init.defaultBranch <branch name>` set name of default branch

### Config levels and file locations

1. `.git/config --local` (default)
2. `~/.config --global`
3. `/etc/gitconfig --system`

## Getting help

`man git`  
`man git-<command>`  
`git help <verb>`

## Getting info

`git status` displays current branch, untracked files, modified files, added files

### diff

`git diff` difference between what has been modified but not staged  
`--staged` difference between what has been staged compared to the last commit (HEAD)
`HEAD` difference between working directory and last commit (HEAD)
`<hash 1> <hash 2> [file]` display difference between two commits
`<branch>` difference between other branch and working directory
`<branch 1> <branch 2>` difference between committed changes in two branches
`<branch 1>...<branch 2>` changes that occurred since branch 2 was started

### Working with logs

`git log` lists commits in reverse chronological order  
`-<n>` shows last nth commits  
`<commit>` only display commits that are older than a particular commit  
`-p` (patch) shows difference introduced by each commit  
`--follow -- <file name>` list commits for a specific file  
`--all --grep='<pattern>'` limit results to commit messages that match the pattern  
`-S <pattern>` look for commits in which the pattern was introduced or changed in the code

`git ls-files` list files in index

`git show --abbrev-commit --name-status [HEAD~n]` displays which files were modified in specific commit  
A = added, C = Copied, D = Deleted, M = Modified, R = Renamed

## Making changes

`git add <file>` stages new files and tracked files that have been modified  
`-u` stages all tracked files that have been updated

`git commit` commits any changes that have been staged. Launches editor for commit message  
`-m` accepts inline commit message  
`-a` skips staging area and commits any tracked files that have been modified  
`--ammend` undoes last commit and returns to staging

`git rm <file name>` remove files from working tree and index  
`--cached` remove file from index only

`git mv <original file> <renamed file>` move/rename a file or rename

## Undoing things

`git reset HEAD <file>` unstage files

`git checkout -- <file>` discard files which are not staged

### Undo last commit

`git reset HEAD~1` undo last commit  
`--soft` keep uncommitted changes  
`--hard` remove uncommitted changes

`git revert HEAD` creates a new commit that undoes last commit

Use `reset` when local changes have not been pushed to remote.
`revert` should be used when changes have been pushed to remote but need to be undone.

### Amend last commit

1. Make changes
2. Add file(s)
   - `git add .`
3. Amend commit without changing commit message
   - `git commit --amend --no-edit`

### Amend commit message

`git commit --amend`

## Working with branches

`git branch` - lists all branches  
`git <branch>` - creates a new branch  
`--all` - display local and remote branches  
`-d <branch>` - delete branch which has been merged  
`-D` <branch> - delete branch that has not been merged  
`-v` display last commit on each branch  
`--merged` display only branches which have been merged into current branch  
`--no-merged` display only branches which have not been merged into the current branch  
`--move <old branch name> <new branch name>` rename branch

- `git push --set-upstream [short name] <new branch name>` to set up branch on remote
- `git push origin --delete <old branch name>` to delete old branch on remote

`git checkout <branch | sha1>` - switch to an existing branch | commit

`git switch -c <branch name>` - create a new branch and switch to it automatically

### Merging

1. Switch to branch you would like to merge changes into
   - `git checkout <receiving branch name>`
2. Merge branch with changes into current branch
   - `git merge <merging branch name>`
3. Delete merged branch
   - `git branch -d <merged branch name>`

### Rebasing

1. `git checkout <branch to rebase>`
2. `git rebase master`
3. `git checkout master`
4. `git merge <branch to rebase>`

## Working with Remotes

### Basic operations

`git remote` displays which remote servers have been configured
`-v` displays URLs stored in git for fetching and pulling  
`show <short name>` displays URL and branch information

### Add/remove/disable push

`add <short name> <URL - https://github.com/bunny-thief/[repo_name].git>` adds new remote repository with specified short name  
`remove <short name>` remove remote  
`git remote set-url --push [short name] no_push`disable push to remote

### Fetching/pulling/pushing

`git fetch [short name]/<branch name>` pulls down all data that you don't have yet from a remote repo
`git pull` downloads and merges remote into current code
`git push [short name] <branch name>` push a specific branch. Only works if another commit hasn't been pushed to remote

### Add/remove remote branch

`git push --set-upstream [short name] <new branch name>` to set up branch on remote  
`git push [short name] --delete <branch name>` to delete branch on remote

### Create local branch from remote branch

`git checkout -b <new branch name> [short name]/<remote branch name>` create local branch from remote branch

### Push existing repo from command line

1. Create local repo and commit changes
2. Create Github repo

- Remote repo name **must match** local repo name
- Don't add README, license or .gitignore files

3. Add remote

- `git remote add origin git@github.com:bunny-thief/<repo name>.git`

4. Set up remote upstream

- `git push -u [short name] <branch name>`

## Connecting to Github with SSH

- [Checking for existing SSH keys](https://docs.github.com/en/free-pro-team@latest/github/authenticating-to-github/checking-for-existing-ssh-keys)
  - [Generating a new SSH key and adding it to the ssh-agent](https://docs.github.com/en/free-pro-team@latest/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)
- [Adding a new SSH key to your GitHub account](https://docs.github.com/en/free-pro-team@latest/github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account)
  - use `cat ~/.ssh/<ssh public key file>` to copy ssh public key
- [Testing your SSH connection](https://docs.github.com/en/free-pro-team@latest/github/authenticating-to-github/testing-your-ssh-connection)

## Git on Ubuntu

### Check Ubuntu version

`lsb_release -a` check Ubuntu version

### Add git to Personal Package Archive (PPA)

`sudo add-apt-repository ppa:git-core/ppa`  
`sudo apt update`
