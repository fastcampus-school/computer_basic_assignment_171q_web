**Comment: 버전관리란 무엇이고, 버전관리 방법에는 어떤 것들이 있는지도 알아봅시다.**


# Git

## Git 이란 
> **소스관리시스템**  

소스 및 파일들을 이력을 관리하는 것

|   a |   n   |   y   | 
|:----|:-----:|------:|
|     |       |       |


<br><br>

## Git 작업초기화 (터미널 작업)

1. Git으로 사용할 폴더 생성  
`mkdir <폴더명>`

2. git 초기화 ( 워킹 디렉토리를 git으로 사용하겠다. )  
`git init`
> 해당 디렉토리 이후 생성 되는 파일 및 폴더 등이 변경된 것을 감지함.

3. git에서 무시할 파일 생성 ( 작업환경 공유를 위해초기화와 함께 늘~ 넣어 주는것 )  
`vi .gitignore`
> [https://www.gitignore.io/ ](https://www.gitignore.io/ ) 사이트에 접속하여 
> 개발에 필요한 환경을 입력하면 자동으로 GIT이 무시할 코드를 자동으로 생성하여 준다.
> 개발 초기 repository folder 생성시 꼭! 반드시! 추가해 줘야 다른 작업자와의 환경을 공유할 수 있음.

<br>
<br>
## 터미털 명령

* ##### 현재 워킹 상태 확인
`git status`

* ##### add
`git add <파일명>`

* ##### Commit
`git commit`

* ##### push
`git push`

* ##### branch 생성
`git branch `

* ##### branch 이동
`git checkout <branch명>`

* ##### branch 목록보기
`git branch`

* ##### branch 삭제
`git branch -d`

* ##### branch 하위 목록 생성
`git branch <생성명> <상위branch>`

* ##### branch 구조보기
`git branch --graph`

* ##### merge 하기  
 `git merge <머지 할 commit Num>`
 > merge 는 merge를 통합할 곳에서 통합될 곳을 commit Num 넘버를 가져온다.

* ##### commit 되돌리기 (reset 이후 전부 취소 )  
`git reset --hard <commit Num>`
> 특정한  commit Num 이후 다 삭제 

* ##### commit 되돌리기 취소   
`git reset --hard ORIG_HEAD`

* ##### 특정한 Commit 만 취소시 (부분취소)  
`git revert <commit Num>`
> 특정한 commit만 삭제시


<br>
<br>
## 원격저장소

* ##### 원격저장소의 저장소에 내용을 복사
`git clone <URL>`
> 원격저장소와 같은 내용을 local에 동일하게 복사한다.
> url 은  github.com 참조

* ##### 원격저장소의 저장소 목록 확인  
`git remote`

* ##### 원격저장소의 저장소 추가
`git remote add`

* ##### 원격저장소의 정보 확인
`git remote show`

* ##### remote 삭제
`git remote rm`

* ##### push 하기
`git push`
> push 하기를 위해서는  pull을 선행해야 한다.

* ##### pull 하기
`git pull`

<br>
<br>
## MAC 터미널 명령어

`cd` = 해당 경로로 이동  
`pwd` = 현제 경로를 표시합니다.  
`ls` = 조건 검색어 - ls *st* 파일 이름 중간에 st 를 포함한 모든 파일을 표시합니다. -a 숨김파일도 표시합니다.  
`cp` = 원본복사 - cp web /bin "web"폴더를 /bin에 복사합니다.  
`mv` = 원본이동 - mv web /bin "web"폴더를 /bin으로 이동합니다.  
`rm` = 원복삭제 - rm web or rm -r web "web"폴더를 삭제 합니다.  
`mkdir` = 폴더 생성
`rmdir` = 폴더삭제 (휴지통에 남는게 아니니 주의)  
`touch` = 파일생성  
`grep` = 파일안 내용찾기 - grep head index.php "index.php" 에서 head 가 포함된 낱말을 찾어 냅니다.  
`ln` = 링크 - ln -s /bin/web/ apath main "/bin/web/" 의 해당경로를 apath main 으로 링크합니다.  
`who` = 현제 접속 또는 로그인중인 모든 사용자를 찾어줍니다.  
`ps` = ps(옵션) - 현제 실행중인 모든 프로세서 표시합니다.  
`kill` = kill ichat - ichat 프로세서를 강제 종료 합니다.  
`find` = 조건검색어 - find /root/ -name *password* 파일이름에 password 를 포함한 파일을 /root 폴더에서 검색합니다.  
`whereis` = whereis ichat "ichat 가 있는 프로세서 경로를 표시합니다.
`sudo` = sudo vi /etc/php.ini      root 권한으로 /etc/ 폴더에 php.ini 파일을 vi로 편집합니다.  
