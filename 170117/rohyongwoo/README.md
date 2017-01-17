#과제 - 노용우

###2017년 1월 17일 화요일

##버전관리란?
프로그램의 *소스 코드*, *문서*, *그래픽 및 관련 파일* 들을 대단위 **소프트웨어** 로 관리하는 것. 

> **버전관리 소프트웨어**는 해당 프로그램의 모든 프로그래머 및 개발자들이 프로그램을 *개정한 사항* 들을 추적하는 데 사용되는 **데이터베이스** 를 제공한다.
> 
> 동일 목적의 데이터에 대해 각 시점의 버전을 기록하여 **코드의 변화**를 관리하는 것.

##버전관리 종류

####1. 원시적인 버전관리 방법
  * 파일 복사 후 저장

####2. 로컬 버전관리 시스템(LVCS)
  * 버전을 **개인별로 관리**. 대표적으로 RCS

> 각 리비전 간 패치 세트라는 데이터의 차이점을 특별한 형식의 파일에 저장, 특정 시점의 파일 내용을 보고 싶을 때 해당 시점까지의 패치들을 모두 더하여 파일을 만들어냄
> 
> 협업이 어렵고, DB 데이터가 잘못되면 모든 이력을 잃어버릴 우려가 있음

####3. 중앙집중식 버전관리 시스템(CVCS)

![alt CVCS](images/CVCS.png)

  * **하나의 서버에 여러 클라이언트**들의 파일을 저장하여 관리하는 형태로 다수의 개발자들의 협업과 관리를 위해 탄생

> 대표적으로 CVS와 좀 더 발전된 형태의 SCN이 있는데, SCN은 현재까지도 많은 곳에서 활용되고 있음
> 
> CVCS는 중앙 서버가 잘못되면 연결된 모든 클라이언트들의 버전관리 작업이 중단되고, 데이터가 날라가기도 하는 날에는 모든 이력을 잃어버리게 되는 문제가 있음

####4. 분산 버전 관리 시스템(DVCS)

![alt DVCS](images/DVCS.png)

  * **로컬 저장소와 원격 저장소 모두**를 가지는 버전관리시스템

> 기존 VCS에 비하여 강력한 브랜치, 병합 기능을 제공하며, 로컬 저장소만으로 잘 동작하므로 반드시 중앙 서버 연결할 필요 없고, 다수의 원격 저장소를 가질 수 있음
> 
> 대표적으로는 Git, Mercurial이 있으나, 현재 Git이 가장 많이 사용됨
> 
> 하나의 저장소에 대해 여러 개의 브랜치를 만들어 따로 관리 및 패치 적용이 가능
   
##Git Command

Command | Contents
--- | ---
`git init` | 현재 있는 워킹 디렉토리에 **.git** 폴더 생성
`git status` | 현재 워킹 디렉토리 상태 확인
`git clone` | *Remote Repository* 를 통째로 워킹 디렉토리에 복사
`git pull` | *Remote Repository* 의 정보를 가져와 워킹 디렉토리와 병합
`git add` | 새로 만들어졌거나 변경된 파일을 워킹 디렉토리에서 *Stage* 에 올리기
`git commit` | *Stage* 에 올라온 파일을 *Local Repository* 에 올리고 comment 남기기
`git push` | *Remote Repository* 로 파일, comment 보내기
`git log` | History 확인
`git revert` | 이전 커밋 취소


Command | Contents
--- | ---
`git remote` | 워킹 디렉토리와 *Remote Repository* 연결
`git branch {branch name}` | 현재 위치에서 새로운 브랜치 생성
`git checkout {branch name}` | 다른 브랜치로 이동하기
`git checkout -b {branch name}` | 브랜치를 생성하면서 이동하기
`git merge {commit number}` | 현재 브랜치에 해당 커밋을 merge
`git pull origin {branch name}` | *Remote Repository* 에서 해당 브랜치를 로컬로 가져오기
`git reset {mode} {commit number}` | 해당 커밋으로 해당 모드로 이동
`git reset {mode} ORIG_HEAD` | 이전 reset 명령 취소
