7# git-commands
git cheat sheet

## Getting a repository

**git init* initializes a repository

**git clone** <url> [directory] clones a repository

##Getting info

**git status** displays current branch, untracked files, modified files, added files

**git diff** displays what has been modified but not staged
--staged displays the what has been staged compared to the last commit

##Making changes

**git add** <file> stages new files and tracked files that have been modified

**git commit** commits any  changes that have been staged. Launches editor for commit message
-m accepts inline commit message
-a skips staging area and commits any tracked files that have been modified

**git rm** remove files that are currently been track

**git mv <original file> <renamed file>** move/rename a file or rename

##Viewing commit history
