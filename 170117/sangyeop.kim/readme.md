# 버전 관리 (VCS)  


## 개요
> 버전 관리 시스템은 **파일 변화**를 시간에 따라 기록 했다가 나중에 특정 시점의 버전을 다시 꺼내올 수 있는 시스템이다.  

## 이점
> **변경 이력**을 기록을 통해서 변경 된 내용을 공유할 수 있다.  
> **타인이 작업한 내용**을 쉽게 병합할 수 있다.  
> **과거 상태**로 쉽게 복구 가능하다.  
> **여러 분기(Branch)**를 통해 병렬 관리가 가능하다.  

## 종류
> **Subversion**  
> **Mercurial**  
> **Git**     


# Git 명령어  
> `cd <폴더 이름>` : 경로 이동  
> `cd ..` : 경로 뒤로 이동  
> `mkdir <폴더 이름>` : 폴더 생성  
> `rm -rf <폴더 이름>` : 폴더 삭제  
> `rm <파일 이름>` : 파일 삭제  
> `open .` : 해당 파일 파인더에서 열기  
> `ls` : 위치한 폴더의 파일 확인  
> `ls -a` : 위치한 폴더의 숨겨진 파일까지 확인  
> `pwd` : 현재 위치하고 있는 경로 확인  
> `git init` : local repository 생성  
> `git status` : git 상태 확인  
> `git add <파일 이름>` : git stage 에 추가  
> `git add -A` : 수정되거나 추가된 파일 전부 stage 에 추가  
> `git commit` : commit 추가  
> `git -m "내용"` : commit 추가    
> `git log` : history 확인  
> `git log -p` : 수정된 내용 포함한 history
> `git clone <repository url 주소>` : 서버에 저장된 파일 저장  
> `git push` : remote repository 로 파일 추가  
> `git pull` : remote repository 에서 파일들 받아옴  
  
 