**Comment: 터미널과 git 명령어 정리 잘하셨네요!! 과제1. 버전관리란 무엇이고, 버전관리 방법에는 어떤 것들이 있는지도 알아봅시다.**


### 터미널 기본 명령어 

> **pwd**  
> 현재 경로
> **ls** 
>  해당 디렉토리 안에 무슨 파일이 있는지
> **mkdir** 
>  make directory
> **cd** 
> directory 이동
> **..** 
> 상위 이동
> **~** 
> Home directory
> **rm** 
> 일반 파일 삭제
> **rm -rf** 
> directory 삭제(rmdir과 같음)

----------------------------------------

### git 기본 명령어
> **git init** 
> present working directory에 .git 폴더 생성
 git init해서 local repository 생성하자마자 실행, conflict 방지
 
> **git status** 
> pwd 상태 확인
>
> **git clone**
remote 저장소를 통째로 워킹 디렉토리에 복사

> **git pull**
>  remote의 정보를 가져와 워킹 디렉토리와 병합
>  
> **git add 파일이름**
 새로 만들어졌거나 변경된 파일을 working directory에서 stage
>
> **git reset HEAD 파일이름** 
> unstage

> **git commit -m "내용"**
 staged된 파일을 local repo에 올리며 commit message 작성
 
> **git remote add orgin 저장소의http주소** 
> **git push -u origin master** 
> (저장소가 이미 있는 경우의) working directory와 remote repo 연결
> 
> **git push**
>  local repo에서 remote repo로 보내기
>  
> **git log** 
> commit한 내용 확인

### git branch 관련 명령어

> **git branch 브랜치이름** 
> branch 생성
> 
> **git checkout 브랜치이름**
> 다른 branch로 이동
> 
> **git branch 하위(new)브랜치이름 상위(existed)브랜치이름** 
> 하위브랜치 추가생성
> 
> **git branch -D 브랜치이름** 
> branch 삭제
> 
> **git merge 커밋넘버** 
> 상위 branch로 이동한 상태에서, 하위 branch의 마지막 commit number 복사하여 입력하면 merge
> 
> **git log --graph** 
> history 보기
