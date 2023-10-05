# important git commands

### beginner level commands 
- `git init` => initializes empty git repository 
- `git add <files names>` => starts TRACKING your new changes for the next commit.  
- `git add .` => to add all the changes   
- `git commit -m <message>` => this creates a new version based on your prev changes.  
- `git remote add origin <URL>` =>   
 remote : helps to connect to a repo that might not be local to you  
 add : we want to add a remote  
 origin : nickname for remote repository (using url can be tds )  (in system origin==URL)  
- `push origin -u origin master` => pushing a version which is on branch master on origin(URL)  
######
- `git cat-file <flag> <hash>` => flag::  -t(type of object) , -p(print content of the object) ; hash: 5-6 chars 
######
- `git rm --cached <file>` => if we want to remove full file from staging area.
- `git restore --staged <file> ` => the new pushed changes will be back.
- `git add -p` => interactive way to add your changes to your staging area.

## branching  
- `git branch` => to display all branches
- `git checkout -b <branch-name>` => to create a branch
- `git checkout <branch>`   => to move from present to mentioned branch

## merging
- go to the branch into which you want to merge.
- `git merge <branch-you-want-to-merge>` => merges branch