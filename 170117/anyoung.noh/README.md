##Version Control System
###1. 버전관리란 무엇인가?
__VCS : Version Control System__  
버전컨트롤시스템(이하 VCS)은  시간에 따른 소스코드 변경을 관리하는 일종의 소프트웨어이다. 개발자는 지속적으로 새로운 코드를 작성하고 기존의 코드를 변경한다. VCS는 특정 데이터베이스의 모든 변경이력을 코드로 추적하기 때문에 소스코드에 실수가 있었다면 개발자는 이전 버전의 코드를 보며 문제를 해결할 수 있다. 대부분의 소프트웨어 프로젝트에서 소스코드는 매우 중요한 자산이기에 VCS를 이용하여 소스코드의 유실에 대비해야한다.

* 소스코드의 변경이력을 공유할 수 있다.  
* 병렬적으로 작업을 진행하다가 서로의 코드를 쉽게 병합할 수 있다.
* 파일을 이전상태로 되돌리거나 프로젝트 전체를 되돌릴 수 있다.  
* 시간에 따른 변경이력 비교가 가능하다.  
* 누가 문제를 일으켰는지, 언제 생성된 이슈인지 추적이 가능하다.  
* 파일에 문제가 생겼을 시 이전 버전으로 파일 복구가 가능하다.


###2. 버전관리에는 어떤 방법들이 있는가?
####로컬 버전 관리 시스템 
파일의 버전 관리를 위한 가장 간단한 방법은 Directory로 파일을 복사하는 방법이다. 매우 쉬운 방법이지만 실수를 할 여지가 너무 많기때문에 로컬 VCS가 만들어졌다.  
 
-
####중앙집중식 버전관리 시스템(Centralized VCS)
CVCS는 공동작업자가 있을 경우 생기는 문제를 해결하기 위해 만들어졌다. 이 시스템은 모든 파일을 관리하는 서버를 구축해놓고 사용자가 서버에서 파일을 받아 사용하는 방식이다. 프로젝트 관리의 모든 것을 중앙 서버에서 처리하기 때문에 로컬에서는 제약이 많다. 이 시스템의 큰 문제점은 서버에 문제가 생기면  사용자는 정상적인 작업을 진행하기 어려우며, 서버의 데이터가 유실됬을 경우 남는 것은 로컬에 분산된 파일들 뿐이다. 

`ex) CVS, CVSNT, QVCS Enterprise, Subversion`

-
####분산형 버전 관리 시스템(Distributed VCS)
DVCS에서는 사용자가 서버의 데이터를 모두 복제하여 각자의 로컬에 갖게된다. 따라서 서버에 문제가 생겼을 경우 이 복제된 데이터를 사용할 수 있다. 대부분의 DVCS 환경에서는 다수의 리모트 저장소가 존재할 수 있고 사용자들은 동시에 다양한 그룹과 다양한 방법으로 협업할 수 있다.

`ex) Monotone, SVK, Codeville, Bazaar, Git, Mergurial, Fossil, Veracity`

-
####Git
대부분의 VCS 시스템이 관리하는 정보는 파일들의 목록이며 각 파일에 대한 변화(차이점)을 저장한다.  
 __Git의 핵심은 파일 시스템의 Snapshot을 저장한다는 점이다__ Git은 Commit하거나 프로젝트의 상태를 저장할 때마다 파일이 존재하는 그 순간을 중요하게 여긴다. 파일이 달라지지 않았으면 Git은 성능을 위해 파일을 저장하지 않으며 이전 상태의 파일에 대한 링크만 저장한다.  
__Git은 거의 모든 명령을 로컬에서 실행한다.__ 따라서 네트워크의 속도에 영향을 받지도 않는다. 프로젝트의 모든 히스토리가 로컬에 있기 때문에 명령을 처리하는 속도 또한 빠르다. 




##git command 
###BASIC
Command | description
------  | --------
**git --version** | 현재 git의 버전확인 
**git init** |  WorkingDirectory에 Local repository 생성 (숨김 파일로 .git 폴더가 생성됨)
**git status** | WorkingDirectory의 commit되지 않은 변경사항을 조회 
**git add** | 새로 만들어졌거나 변경된 파일을 WorkingDirectory에서 StageArea로 올림  
**git add -A** | 새로 만들어졌거나 변경된 파일을 WorkingDirectory에서 StageArea로 한번에 모두 올리기  
**git commit** | StageArea에 올라온 파일을 LocalRepository에 올리기
**git commit -m** _`"commit message"`_  | StageArea에 올라온 파일을 LocalRepository에 올리고 commit message 콘솔에서 작성 
**git commit** _`filename`_ **-m** | 해당 파일을 StageArea으로 넘긴 후 LocalRepository에 commit하는 과정을 한번에 진행하고 콘솔에서 commit message 작성 
**git commit -a** | 모든 파일을 StageArea으로 넘긴 후 LocalRepository에 commit하는 과정을 한번에 진행  
**git commit -a -m _`"commit message"`_**  | 모든 파일을 StageArea으로 넘긴 후 LocalRepository에 commit하는 과정을 한번에 진행하고  콘솔에서 commit message 작성 
**git diff** | StageArea와 현재 작업트리의 차이 보여줌 (--cached 옵션을 추가하면 StageArea와 Repository의 차이점을 볼 수 있음)
**git mv** _`filename A`_ _`filename B`_ | 기존에 존재하는 파일 A를 새파일 B로 이동한다.
**git checkout** _`filename`_ | StageArea로 옮겨지지 않거나 commit하지 않은 파일의 변경이력을 취소하고 이전 commit 상태로 돌아감

###BRANCH
Command | description
------  | --------
**git branch**  | 현재 존재하는 branch 조회
**git branch -r** | RemoteRepository의 branch 조회
**git branch** _`branch B`_ _`branch A`_ | branch A 에서 새로운 branch B 생성
**git branch -d** _`branch A`_ | branch A 를 삭제 
**git branch -m** _`branch A`_ _`branch C`_ | 존재하는 branch A를 새로운 branch C 로 변경한다. 이미 존재하는 branch name이 있을 경우에는 에러가 나지만 -m 옵션을 사용하면 이미 있는 branch에 덮어쓴다 
**git tag** _`tag-name`_ _`branch A`_ | branch A의 현재시점에 tag-name 이라는 `tag`를 붙인다. (git tag 를 입력:  현존하는 태그 목록 조회)
**git checkout** _`branch-name`_ or _`tag-name`_ | 해당 branch나 tag로 작업트리를 변경
**git merge** _`branch A`_ | branch A를 현재 branch와 병합
**git merge** _`branch A`_ **--squash** | branch A의 모든 commit을 하나의 commit으로 만듦
**git rebase**_`branch A`_ | branch A의 변경사항을 현재 branch에 적용
**git cherry-pick** _`commit-number`_ | commit-number의 특정한 commit만을 선택하여 현재 branch의 commit으로 만듦

>merge와 rebase는 비슷해보이지만 로그에서 차이가 남.
rebase는 현재 브랜치와 병합할 브랜치의 로그가 모두 선형적으로 남는다.
[Merge vs Rebase](http://dogfeet.github.io/articles/2012/git-merge-rebase.html)


###LOG
Command | description
------  | --------
**git log** | commit log 조회
**git log -p** | 어떤 부분들이 수정되었는지 history와 함께 보여줌 
**git log --graph** | branch tree 조회
**git revert** _`commit-number`_ | 해당 commit만 취소
**git reset** _`commit-number`_ | 해당 commit상태로 되돌아간다
**git reset HEAD^** | 최근 1개의 commit 취소
**git blame** _`file-name`_ | commint-number와 commit한 사람등의 정보 조회
**git rebase -i**_`range of commit`_ | 대화형 모드로 commit 순서를 변경하거나 병합하는 등의 작업 가능

>reset 옵션  
>**git reset** _`commit-number`_ **--soft**: local repository만 되돌린다.  
>**git reset** _`commit-number`_ **--mixed**: stage area 까지 되돌린다.  
>**git reset** _`commit-number`_ **--hard** : Working directory까지 되돌린다.


###REMOTE REPOSITORY
Command | description
------  | --------
**git clone** _`URL(RemoteRepository address)`_| RemoteRepository를 통째로 Working directory에 복사(로그포함)  
**git fetch** | RemoteRepository의 변경사항을 가져와서 branch를 갱신
**git pull** | RemoteRepository의 정보를 가져와 WorkingDirectory와 병합  
**git push** | RemoteRepository로 파일과 commit message보내기 
**git remote add A B** | 새로운  RemoteRepository A를  B(저장위치)에 추가
**git remote show A** | RemoteRepository A의 정보조회
**git remote rm A** | RemoteRepository A를 제거 