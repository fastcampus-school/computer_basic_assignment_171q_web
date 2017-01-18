**Comment: ctr+c/ctr+v는 지양합시다~**


# 과제
###과제 1. 버전관리란 무엇이고, 버전관리 방법에는 어떤 것들이 있는지 알아보기
--
###I. 버전관리의 정의와 의의
* __What__ is it?
	* Version control (aka. source control, source code management)
	* 팀 단위로 개발 중인 source code 등을 관리하는 데 사용하며 변경도니 사항들에 숫자나 문자로 이루어진 "버전"을 부해서 구분함.

* __Why__ do we use it?
	* 잘못되었을 때 복구를 돕기 위하여
	* 여러사람이 함께 참여할 경우, 각자가 수정한 부분을 팀원 전체가 동기화하는 과정을 자동화하기 위하여
	* 대규모 수정 작업을 더욱 안전하게 진행하기 위하여
	* "Branch"를 통해 프로젝트에 영향을 최소화 하면서 새로운 부분을 개발하기 위하여
	* etc.  

* Version Control "System"
	파일 변화를 시간에 따라 기록했다가 이후에 특정 시점의 버전을 다시 꺼내올 수 있는 시스템이다. 동일한 정보에 대한 여러 버전을 관리하게 되며, 버전을 통해 시간적으로 변경 사항과 변경 사항을 작성한 작업자를 추적할 수 있다.
	* Local VCS: 간단한 데이터베이스를 사용하여 파일의 변경 정보 관리.
	* Centralized VCS: 파일 관리 서버가 별도로 있고 클라이언트가 중앙 서버에서 파일을 받아(checkout) 사용할 수 있다. 대표적으로 _Subervision, Perforce_ 등이 있다.
	
	![diagram]
(http://iissnan.com/progit/book_src/figures/18333fig0102-tn.png)

	* __Distributed VCS__: 클라이언트가 파일의 마지막 스냅샷을 가져오는 것이 아니라 저장소 자체를 '복제'하게 된다. 서버에 문제가 생길 경우 이 복제물로 작업이 가능하며 서버를 복원할 수도 있다. 동시에 다양한 그룹과 다양한 방법으로 협업이 가능하다. 대표적으로 _Git, Mercurial, Bazaar, Darcs_ 등이 있다.
	
	![diagram 2](https://code.csdn.net/CSDN_Code/progit/blob/master/figures/18333fig0103-tn.png)
	
	
--
	
	
###과제 2. git command 정리하기

#####CREATE
* create a new local repository

```
git init
```
* clone an exisiting repository

```
git clone ssh://user@domain.com/repo.git
```
--
#####LOCAL CHANGES
* changed files in your working directory

```
git status
``` 
* Add all current changes to the next commit

```
git add .
```
* add some changes in <file> to the next commit

```
git add -p <file>
```
* commit all local changes in tracked files

```
git commit -a
```
--
#####COMMIT HISTORY
* show all commits, starting with newest

```
git log
```

* who changed what and when in <file>

```
git blame <file>
```
--
#####BRANCHES & TAGS
* list all existing branches

```
git branch -av
```

* switch HEAD branch

```
git checkout <branch>
```

* create a new branch based on your current HEAD

```
git branch <new-branch>
```

* delete a local branch

```
git branch -d <branch>
```
--
#####UDPATE & PUBLISH
* list all currently configured remotes

```
git remote -v
```

* add new remote repository, named <remote>

```
git remote add <shortname> <url>
```

* download changes and directly merge into HEAD

```
git pull <remote> <branch>
```

* publish local changes on a remote

```
git push <remote> <branch>
```
--
#####MERGE & REBASE
* merge <branch> into your current HEAD

```
git merge <branch>
```

* rebase your current HEAD onto <branch>

```
git rebase <branch>
```
--
#####UNDO
* discard all local changes in your working directory

```
git reset  --hard HEAD
```

* discard lcoal changes in a specific file

```
git checkout HEAD <file>
```

* revert a commit

```
git revert <commit>
```
--

Reference
1. http://flowerykeyboard.tistory.com/1


