#**버전관리시스템(VCS)**
-------------------------------------
####누구에게 필요한가?
	1. 소스 코드를 작성 혹은 관리하는 모든 개발자
	2. 파일에 대한 변경 이력 관리가 필요한 사람
####왜 필요한가?
	1. 	소스 백업이 편리하다
	2.	빌드 후 버그 발생 시 빌드 이전 소스로 복구가 용이하다
	3.	다수 작업자 혹은 다른 장소에서의 소스 동기화가 편하다
	4.	동일 소스에서 동시에 다른 프로젝트가 진행 되더라도 소스 병합이 편하다
	5.	어느 시점에 누가 무슨 이유로 소스를 변경했는지에 대한 변경 이력 관리가 용이하다
#**버전관리 방법**
----------------------------------------
버전 관리 방법에는 크게  **로컬 버전 관리**, **중앙 집중식 버전 관리** 그리고,**분산 버전 관리** 방법이 있다.  
####**1. 로컬 버전 관리 시스템(Local VCS)**
버전을 관리하는 가장 쉬운 방법으로 작업 중인 내용을 다른 디렉토리에 복사해 관리하는 방법. 간단한 데이터 베이스를 사용하여 파일의 변경 정보를 관리한다.  
####**2. 중앙 집중식 버전 관리 시스템(Centralized VCS)**
여러 개발자와 함께 프로젝트를 진행할 때 사용하는 시스템이다. 중앙 서버에서 모든 파일을 관리하며, 여러 클라이언트가 중앙 서버에서 파일을 받아 사용할 수 있다.  
관리자가 프로젝트에 참여한 사람들 중 누가 무엇을 하는지 관리가 용이하지만, 중앙 서버가 다운되면, 버전 관리가 불가능하며백업도 불가능하다. 또한 하드디스크에 문제가 생기면 모든 자료 및 히스토리를 잃게 된다.  
####**3. 분산 버전 관리 시스템(Distibuted VCS)**
분산 버전 관리 시스템에서는 클라이언트가 파일의 마지막 스냅샷을 가져오는 것이 아니라 저장소 자체를 복제하게 된다. 서버에 문제가 생겨도, 클라이언트가 복제한 복제물로 서버를 복원할 수 있다. 대표적인 예로는 Git, Mercurial등이 분산 버전 관리 시스템에 속한다.  
   
#**git 명령어(command) 정리하기**
1.**git init** : git 초기화. working directory에 .git 폴더가 생성됨. local repo 생성.  
>		**git init**을 한 번 하면 **.gitignore**를 작성해 주어야 편하다.  
	  *gitignore.io*에서 설정 가능.  

2.**git status** : working directory상태 확인. staging area에 올라간 파일들.  
3. **git add 파일명** : working directory에서 staging area로 파일이 이동.  
4. **git add -all** or **git add -A** : staging area에 모든 것을 올리겠다.  
5. **git commit** : staging area에서 local repo로 이동.  
>		commit 단위는 기능 단위를 기준으로 한다.  
      
6.**git commit -s**: commit message 작성 후, local repo로 파일이 이동.    ubuntu는 commit meesage창에서 ctrl+o로 저장하고, ctrl+x로 끝내기 하면, 자동으로 commit됨.  
7. **git commit -m {커밋할 메시지 내용}"** : 커밋 메세지를 바로 입력.  
8. **git commit -a** : staging area로 모든 파일을 올리겠다는 의미.  
9. **git commit -a -m {커밋 메세지 내용}** : staging area로 모든 파일을 올리고, 커밋 메세지까지 입력시키겠다는 의미.  
10. **git log** : commit 이력을 보여줌.  
11. **git log --oneline**: git log들을 한 줄씩만(commit 번호만 출력) 보여줌.  
12. **git commit --amend** : commit message만 수정을 원할 경우.  
13. **git diff {파일명}** : 파일 변경된 내용을 보여줌(git add 하기 전 상태에서).   
14. **git log -p** : 변경된 내용을 보여줌.  
15. **git reset --hard {commit번호}** : 특정 commit 번호로 reset: local repo엔 특정 commit상태로 reset됨.  
16. **git reset --hard HEAD^1**: 마지막 commit 1개를 reset시킴.  
17. **git reset --hard HEAD~~**: HEAD는 현재 브랜치를 가리키는 포인터이며, 마지막 커밋의 스냅샷이다. 이 명령어는 git init하고 처음 commit했을 때의 commit버전으로 reset시킨다는 의미.  
18. **git reset --hard ORIG_HEAD** : 마지막으로 reset 시켰던 commit 버전으로 원복시킴.reset 실행 전의 상태로 되돌림.  
19. **git reset HEAD {파일명}** : staging area에 있는 파일을 working direct으로 마지막 commit상태로 reset시킴.  
19.  **git show {commit번호}** : 해당 commit 내용을 show.  
20. **git checkout {브랜치명}** : 해당 브랜치로 이동.  
21. **git checkout -b {브랜치명}** : 해당 브랜치를 하나 만들고, 그 브랜치로 이동.  
22. **git branch -v**: 브랜치들의 최종 commit 상태를 보여줌.  
23. **git branch -D {브랜치명}** :  해당 브랜치명 삭제.  
