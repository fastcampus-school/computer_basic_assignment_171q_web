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
1.pwd   
현재위치 확인
2.cd ..   
상위폴더로 간다   
3.cd 하위폴더이름   
하위폴더로 간다.   
4.mkdir  
폴더생성  
5.rm -rf 폴더이름  
폴더삭제.   
6.rm 파일이름  
파일삭제

##git 명령어
1.git init   
로컬 레포터지터리 생성      
2.git status     
깃 상태를 보여줌 브랜치나 이것저것  
3. git add 파일이름     
파일을 스테이지 에어리어로 올림.  
4.git commit 파일이름  
파일을 로컬 레포터지터리로 옮김  
5.git remote origin 기트허브주소
6.git push origin master  
화면

```
첫 번째 인덱스 html 파일을 생성하였습니다.
git 명렁어 실습 중입니당.
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

5.git commit -m "문장"   
커밋에 문장 쓸떄    
6.git log    
깃 히스토리를 보는것    
7.git add -A    
다 넣는거임 스테이지 에어리어로   
8.git reset HEAD 파일명.   
스테이지 에어리에 있는건 끌어내리는 것     
9.git commit -a -m "한 번에 컷민하기 내용 추가 "     
한번에 커밋해서 로컬 레포지터리로 올려버린다    
10.git clone 기트허브주소     
주소에 있는 기트허브를 내 워킹 디렉터리로 들어오게한다   

* git log -p   
변경된 사항을 볼수있다

* git push 
푸쉬를해서 리모트 레포지터리 간다

* git reset --hard 커밋번호    
커밋번호까지 리셋을 시켜줘버린다

* git reset --hard ORIG_HEAD     
리셋 했던 것을 다시 마지막 커밋상태로 돌려준당

* git revert --hard 커밋번호    
커밋번호로 리벌트를 한다    

* vi .gitignore    
이그노어에 넣어두는 애들은 다 무시해버린다    
git init 하자말자 쓸것

* git branch 브랜치명    
브랜치를 만들수 있다.

* git checkout 브린채명    
브랜치 체크아웃을 옮겨주는 변수

* git merage 커밋변수    
 커밋변수 지점으로 합병을 시켜줌





