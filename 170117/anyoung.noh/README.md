##버전관리란 무엇이고 어떤 방법들이 있는가?




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