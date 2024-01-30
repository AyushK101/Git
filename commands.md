# official docs : https://git-scm.com/docs

# cheetsheet :  https://quickref.me/git

> for associated flags/properties with commands , use :
> `git <command> -h`


### beginner level commands

- `git init` , `git add <files names>` , `git add .` , `git commit -m <message>`
- `git add -p` => interactive way to add your changes to your staging area.

- `git remote add origin <URL>` =>  
  remote : helps to connect to a repo that might not be local to you  
  add : we want to add a remote  
  origin : nickname for remote repository (using url can be tds ) (in system origin==URL)
- `push origin -u origin master` => pushing a version which is on branch master on origin(URL)

######

- `git cat-file <flag> <hash>` => flag:: -t(type of object) , -p(print content of the object) ; hash: 5-6 chars

## undoing changes :

- `git rm --cached <file>` => if we want to remove full file from staging area.
- `git restore --staged <file> ` => the new pushed changes will be back.
-

## stashing :
- kind of additional area beyond working directory , where all temporary changes are saved , later can be utilized .

## diff :
- `git diff <filename>{for selective}`

## branching

- `git branch` => to display all branches
- `git branch <branchName>` : create branch
- `git checkout <branch>` => to move to mentioned branch
- `git checkout -b <branch-name>` => create + checkout
- `git branch -D <branchName>` : delete branch

> `checkout in between changes of branch ?`

## merging

- go to the branch into which you want to merge.
- `git merge <branch-you-want-to-merge>` => merges branch

## configurations

- git config --list | exit: :q

## syncing with remote :

- fetch , pull , push
  > `fetching a particular pull request as maintainer : ` git fetch origin <pull/<pr'sId>/head:<pr'sBranchCreation>>

## Merge conflict :

- more than one code on same positions

# MERGING vs REBASING

- `merging`:

  - creates extra merge commit
  - no linear commit history
  - `git merge <branch>`

- `rebasing` :
  - no merge commit
  - Linear commit history
  - `rewrites commits`
  - `git rebase <branch>`
  - merge conflicts : `add & git rebase --continue`

# CHERRY PICKING

- allow individual commits to be picked to current HEAD without disturbing the history.
  > when to use ? - team collaborations - hotFixes
- `git cherry-pick <commit-id>`

# tags & releases

- package software with release notes & link to binary files , for other people to use.
  > in right navbar of repo on github

# git hygiene

- master is always `ready-to-deploy`
- work on branches
- 1 feature/fix/update = 1 branch
- commit often
- good commit messages & branch names
- never merge your own PR
- delete the merged branches
- don't use git rebase when >1 developers are working

# github exploration

- ## Setup and Config
- git
- config
- help
- bugreport
- Credential helpers
- ## Getting and Creating Projects
- init
- clone
- ## Basic Snapshotting
- add
- status
- diff
- commit
- notes
- restore
- reset
- rm
- mv
- ## Branching and Merging
- branch
- checkout
- switch
- merge
- mergetool
- log
- stash
- tag
- worktree
- ## Sharing and Updating Projects
- fetch
- pull
- push
- remote
- submodule
- ## Inspection and Comparison
- show
- log
- diff
- difftool
- range-diff
- shortlog
- describe
- ## Patching
- apply
- cherry-pick
- diff
- rebase
- revert
- ## Debugging
- bisect
- blame
- grep
- 