
# version control system 
- version: a particular state of a software.

- it is a software tool to manages versions , changes in a software.
- helps us track changes, manage versions and their rollback , compare changes in versions , log the changes , collaborations etc.
- ex: mercurial , git etc.

## centralized vs distributed VCS
<img src="/home/ayush10nov/Desktop/git/Screenshot from 2024-01-08 23-09-24.png">

# git : 
- global information tracker OR GodDamn Ideotic Truckload

- open-source , easy code integrity , secure , flexibility etc 


# important theory 
- whenever we code , it can lies in any one of the following : working area , staging , repo
### working area
- the files/changes which are not in your staging area and maybe currently not handled by git are in working area. These files/changes are also called as untracked files. 
### staging area 
- files and changes which are surely going ot be part of hte next commit are in staging area. (i.e. a file/change when we do git add)
- staging area is the place where git knows what will change b/w the current and next commit.
### repo area (hard disk (storage))
- all our commits lives here.
### repository 
- storehouse of codebase , which tracks all changes made to a files in your project , building a history over time.
- a new version => a new commit : commit message is version's name.  



### how exactly internally git stores data 
- git has two types of data : blob and tree  
- internally git is a <key,value> datastore.  
- key => hash of the data we want ot store  
- value => actual data  
- for same data this hash will be same  
- git stores the actual (compressed) data in a blob (big large object) and some metadata in the header 

- inside objects of .git , we actually stores the blobs  
- from 40 char hash , first two are used as folder name  (tree commands work in powershell not bash)    
- inside git content is only stored once.  

#### how git handles directories ?
- tree: stores information about directories and their content.  
- tree contains pointers to other blobs and trees.  

- git internally does a lot of optimization , the objects are stored in compressed form. 
- it mainly stores data about the change & algorithmically shows us the file content with that change.
#### commit 
- commit is also stored as an object(this object is an commit object)  
- every commit object points to a tree  
- the commit object has data of author and committer , data , message , parent commit(if there ) etc


# one interesting test-case 
- when one commit for one feature and you committed , but you forget some code.
- you can add code and then change the commit by `git commit --amend -m"<message>"`
- but git will still create a new commit object altogether .


### head , branch 
- `head` points to the latest commit and branch `git log --oneline`

# branching , merging
- you can maintain multiple parallel states of your project.
- by default , git gives you one state of the project.
- RECOMMENDED industry practice : for every feature you should have a new branch.
- generally , production brach , testing server branch , other features.
- 

## important case : if remote repo has other commits than your local 
- then you can't directly push because of different commit history.
- ALERT : don't ever do force push , other teammate commits might get deleted . direct firing. 
- correct order : add => commit => pull => push 
-`git pull origin master` => first pull changes , then push


## merge conflict 
- base , incoming , current state .

## pull requests 
- requesting a branch , that i have new changes in my branch and after reviewing them , please merge them.
- if not collaborator :
- fork 
- clone 
- making PR (selecting repo , branch of mine from which pr should be raised and selecting branch of orignal contributor in which i want to merge ) ( comments etc)


### remaining 
- squashing , cherry-picking , fetch  , merge etc

## ignore files
- not going to be tracked by git :
- for files syntax : `<filename`

## markdown 
- 
```javascript
//this will work as javascript code snippet
```

## alias
- `git config --global alias.<aliasName> "<command>"`

## template-ing
- pre written some code snippet which can be used to create a new project
> in setting of repo 

## actions & workflows :
- actions : automation
- workflow : 
    1. everything will be on master branch 
    2. 1 feature/fix/update = 1 branch
    3. mater -> develop -> feature //mostly 
    4. fork -> clone -> branch -> pull request -> merge
    <img src="/home/ayush10nov/Desktop/git/Screenshot from 2024-01-09 00-21-07.png">
    