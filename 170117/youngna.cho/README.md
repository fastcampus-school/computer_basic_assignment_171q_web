


#Git using Terminal
#####ETC git commands
* git config --list
* git --help
* ls -a :show all files even hidden files)
* rm -rf folder : delete a folder
* open . :open a curren foler)
* cd .. : move to previous folder

##git Initialize(로컬 레포 생성)
1. git --version : git version check
2. git init : initializing git local repo creation
3. ls -a (shows git file)

##git file Add
1. git status : status check
2. create file
3. git add file_name.ext : add action
4. git add -A: add all files

###Git Unstage
* git reset HEAD file.ext

## git Commit and msg
1. git commit -m "xxx" 또는 git commit (new window) : commit and commit msg 
2. git log : history check
3. git commit -a -m "XX": skip add action and commit right away 
4. git commit file.ext -m "XX": commit certain file

##git Clone (remote repo)
* git clone url-copy&paste
 
##git Push
* git push: 해당 브랜
* git push --all (for all)

###git Reset and Recovery
* git reset --hard HEAD^ : reset to previous
* git reset --hard HEAD~# : reset to #stage before (#=2: 두개 삭제)
* git reset --hard ORIG_HEAD

###git Branch
* git checkout -b name
* git branch name & git checkout name (위와 같은 결과)
* git branch : check list of branches.
* git checkout: move to another
* git log --all --graph: see graphs of commit/branches
* git branch -d name : delete a branch
* git push --all. : push all branches

###git remove and add new remote repo
* git remote set-url origin git://new.url.here
* git remote rm origin and git add remote url

## .gitignore (레포생성후 바로 생성)
1. git init
2. 바로 vim .gitignore
3. gitignore.io
4. ctrl c, ctrl v
5. :wq
6. initial commit


