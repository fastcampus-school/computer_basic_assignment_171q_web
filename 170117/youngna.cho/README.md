#버전관리
##버전관리(Version Control)란?
> 버전관리 시스템은 파일의 변화를 시간에 따라 기록/추적하여 과거 특정 시점의 버전을 다시 불러올 수 있는 시스템이다. 
> 모든 종류의 파일을 버전관리 할 수 있다. 

###이점
>* 변경 이록 기록과 내용 공유 가능
>* 타인과의 작업 병합 가능
>* 과거 상태로 복구 가능
>* 브랜치 활용으로 병렬관리 가능

###버전관리의 방법
####1. 로컬 버전 관리 시스템
> 데이터베이스에 파일의 변경 사항을 기록하는 시스템으로 가장 간단한 버전관리 시스템이다.
> 
![](https://git-scm.com/figures/18333fig0101-tn.png)

>이를 활용한 시스템 툴 **RCS**
>	: 수정 버전들 간의 patch-set라고 하는 데이터의 차이점들을 특별한 형식으로 파일에 저장하여 필요에 따라 불러올 수 있다. 


####2. 중앙집중식 버전 관리 시스템
>**Centralized Version Control Systems(CVCS)** 
>
> 버전 관리 되는 모든 파일을 저장하는 하나의 중앙서버와 이 서버에서 checkout해서 파일들을 가져오는 다수의 client가 존재한다. 
> 
![](https://git-scm.com/figures/18333fig0102-tn.png)
> 
>로컬VCS보다 client관리가 쉽지만 중앙서버의 문제 발생시 속수무책. 

####3. 분산 버전 관리 시스템
>**Distributed Version Control Systems(DVCS)**
>
> Git, Mercurial, Bazzar, Darcs etc...
>
> 중앙집중식 버전관리 시스템의 문제 해결을 위해 개발되었다.
> 
> ![](https://git-scm.com/figures/18333fig0103-tn.png)
> 
> 파일들의 저장 repository를 통째로 복제하여 관리하기 떄문에 문제 발생시에도 복제된 repo.에서 부터 복구 가능하다. 즉, checkout때마다 전체 백업이 일어나는 방식을 갖는다. 
> 또한 원격 저장소(remote repo.)를 가질 수 있기에 동시에 여러 개발자들과의 협업에 용이하다.


--------------

#Git using Terminal
#####ETC git commands
* `git config --list`
* `git --help`
* `ls -a` :show all files even hidden files)
* `rm -rf folder` : delete a folder
* `open . `:open a curren foler)
* `cd .. `: move to parent folder

##git Initialize(로컬 레포 생성)
1. `git --version` : git version check
2. `git init` : initializing git local repo creation
3. `ls -a `(shows git file)

##git file Add
1. `git status` : status check
2. create file
3. `git add file_name.ext` : add action
4. `git add -A`: add all files

###Git Unstage
* `git reset HEAD file.ext`

## git Commit and msg
1. `git commit -m "xxx"` 또는 `git commit` (new window) : commit and commit msg 
2. `git log` : history check
3. `git commit -a -m "XX"`: skip add action and commit right away 
4. `git commit file.ext -m "XX"`: commit certain file

##git Clone (remote repo)
* `git clone url`-copy&paste
 
##git Push
* `git push`: 해당 브랜
* `git push --all` (for all)

###git Reset and Recovery
* `git reset --hard HEAD^` : reset to previous
* `git reset --hard HEAD~#` : reset to #stage before (#=2: 두개 삭제)
* `git reset --hard ORIG_HEAD`

###git Branch
* `git checkout -b name`
* `git branch name` & `git checkout name` (위와 같은 결과)
* `git branch` : check list of branches.
* `git checkout`: move to another
* `git log --all --graph`: see graphs of commit/branches
* `git branch -d name` : delete a branch
* `git push --all` : push all branches

###git remove and add new remote repo
* `git remote set-url origin git://new.url.here`
* `git remote rm origin` and `git add remote url`

## .gitignore (레포생성후 바로 생성)
1. `git init`
2. 바로 `vim .gitignore`
3. gitignore.io 사이트에서 
4. ctrl c, ctrl v
5. :wq
6. initial commit


