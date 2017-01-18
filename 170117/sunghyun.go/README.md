#버전관리 시스템(Version Control System - VCS)

###버전 관리 시스템이란?

>
파일이나 파일 묶음의 버전을 정기적으로 기록해뒀다가 나중에 파일의 특정버전을 요청받았을 때 되돌릴 수 있는 능력을 가진 시스템

##버전관리 시스템의 종류
1.  local VCS(로컬 버전 관리 시스템) 
2.  중앙집중식 버전 관리 시스템(Centralized VCS - CVCS)
3. 분산 버전 관리 시스템 (Distributed VCS - DVCS)


##1. local VCS(로컬 버전 관리 시스템)
<br>
###로컬 버전 관리 시스템이란?



| 정의  | 장점  | 단점  |
|---|---|---|
|로컬 버전 관리 시스템이란 버전을 관리하기 위해 디렉터리를 통해 파일을 복사하는 방법  |  간단하고 자주 사용한다.|  엉뚱한 파일을 덮어쓰거나 의도하지 않은 위치로 복사하는 등의 실수가 발생할 수 있다는 단점이 있다.|
<br>

### RCS
* 로컬 버전 관리 시스템의 **단점**을 예방하기 위해서 나온 시스템으로써 각 버전 별로, 패치 세트라고 하는 데이터의 어느 부분이 변경되었는지를 저장해둔다. 그리하여 **특정 시점의 파일 내용을 보고 싶을 때 해당 시점까지의 패치 세트를 모두 더하여 파일을 만들어내는 방식이다.**

<br>
<br>
![center](http://cfile4.uf.tistory.com/image/2735823A543782360924C7)
<br>
<br>
##2.중앙집중식 버전 관리 시스템(Centralized VCS - CVCS)
<br>

###중앙집중식 버전 관리 시스템이란? 

| 정의  | 장점  | 단점  |
|---|---|---|
|프로젝트를 진행할 때 다른 개발자와 함께 작업해야하는 경우 사용되는 시스템으로써 파일을 관리하는 서버가 별도로 있고 클라이언트가 중앙 서버에서 파일을 받아 사용|1.프로젝트에 참여한 사람이면 누가 무엇을 했는지 알 수 있다.  2.관리자는 누가 무엇을 하고있는지 볼수도 있다. |만약에 서버에 문제가 생긴다면 그동안 다른 사람 모두다 작업을 할 수 없으며 백업할 방법도 없다. 물론 이미 받아놓은것을 바탕으로 복구할 수 있겠지만 없다면 다 날아간것이다.

<br>

![center](http://cfile2.uf.tistory.com/image/2627F63A5437825E1D5C37)

##3.분산 버전 관리 시스템 (Distributed VCS - DVCS)
<br>
###분산 버전 관리 시스템이란?
<br>

| 정의  | 장점  | 단점  |
|---|---|---|
|로컬 저장소뿐만 아니라 원격 저장소에도 배포하여 저장할 수 있으며 작업 이력을 관리하고 분기하여 원하는 시점으로 파일을 복원하거나 통합할 수 있는 프로그램  |1.서버에 문제가 생겨도 클라이언트에 존재하는 저장소를 서버로 복사하면 서버가 복구된다. 2. 저장소만 복사하면 어떤컴퓨터에서든 버전을 관리할 수 있다.| 중앙집중식 버전 관리 시스템에 비해 다소 복잡해진다.|


<br>

![distri1](http://cfile26.uf.tistory.com/image/243A263C543782DA172259)

<br>

![distri](http://cfile25.uf.tistory.com/image/22599B3F563A848D06767E)


##기본 명령어

<br>

|명령어|내용|
|----|---|
|pwd |현재위치를 확인한다|
|cd ..|상위폴더로 간다                            |  
|cd 하위폴더이름     |하위폴더로 갑니다               |
|mkdir     |폴더를**생** 생성합니다                    |
|rm -rf 폴더이름    |폴더를 삭제합니다              |
|rm 파일이름|파일을 삭제합니다                      |

<br>


##git 명령어
|명령어|내용|
|----|---|
|git init|로컬 레포지터리를 생성합니다|
|git status|깃 상태를 보여줍니다|
|git add 파일이름|파일을 Stage Area로 보냅니다|
|git commit 파일이름|파일을 ㅣLocal Repository로 보냅니다|
|git remote origin 기트허브주소|기트허브의 주소로 Remote Repository연결합니다**과연 그럴까요?** |
|git push origin master|마스터 브랜치로 파일**은** 보냅니다.|
 
 <br>
 
 
```
첫 번째 인덱스 html 파일을 생성하였습니다.
git 명렁어 실습 중입니다.
# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
# On branch master
#
# Initial commit
#
# Changes to be committed:
#       new file:   index.html
#
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
esc shift ; wq 하면 저장
```

<br>

|명령어|내용|
|----|---|
|git commit -m "문장"|커밋의 내용을 미리 넣어줍니다|
|git log|깃 히스토리를 보는것입니다|
|git add -A|Stage Area 모든 정보를 다 보냅니다|
| git reset HEAD 파일명.| 스테이지 에어리에 있는 파일을 Working Directory 돌려 보냅니다|
|git commit -a -m "한 번에 컷민하기 내용 추가 "|한번에 커밋해서 Local Repository로 올려버립니다|
|git clone 기트허브주소|주소에 있는 기트허브를 나의 Working Directory로 들어오게 합니다|
|git log -p |변경된 사항을 볼수있습니다.|
|git push|push를해서 Remote Repository 갑니다.
|git reset --hard 커밋번호|커밋번호까지 리셋을 시킵니다.|
|git reset --hard ORIG_HEAD |reset 했던 것을 다시 마지막 커밋상태로 돌려줍니다.|
| git revert --hard 커밋번호| 커밋번호로 revert를 합니다|
| vi .gitignore| 이그노어에 넣어두는 애들은 다 무시해버린다  **git init 하자말자 쓸것** |
| git branch 브랜치명 | 브랜치를 만들수 있습니다.  |
| git checkout 브린채명 |브랜치 체크아웃을 옮겨주는 변수입니다 |
| git merage 커밋변수     |커밋변수 지점으로 합병을 시켜줍니다   |
| git diff   |파일 변경사항들을 보여줍니다   |
| git diff 파일    | 해당 파일의 변경사항을 보여줍니다  |  
|  git stash | 변경된 내역들을 스택에 만들고 워킹디렉토리는 깨끗하게 비웁니다  |  
| git stash list   |  스택에 저장된 내역들을 확인할 수 있습니다  |  
|  git stash apply  |   스택에 저장된 최신의 stash를 적용합니다 |  
|   git stash apply stash이름(ex.stash@{0}) | 스택에 저장된 stash중 이름이 같은 stash를 적용합니다 |  
| git stash apply –index    |  Stage 상태로 스택에 저장된 stash를 Stage 상태까지 복원합니다  | 
