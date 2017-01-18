**Comment: git 명령어 정리 잘하셨네요!! :) 과제 1. 버전관리란 무엇이고, 버전관리 방법에는 어떤 것들이 있는지도 알아봅시다.**


# 터미널 git

## Basic
HEAD 히스토리에서 우리의 상태?위치? (어떤 브랜치의 어떤 커밋에 있다)

### 간단한 터미널 명령어
* `pwd` 현재경로
* `ls` 해당 경로안에 있는 파일과 디렉토리 list
	* `-a` 숨김파일 보이기
* `mkdir` 디렉토리 만들기
* `cd` 디렉토리 이동
	* `~` 홈디렉토리 `/` 루트 `..` 상위
* `rm` 파일 삭제
	* `-rf` 디렉토리도 삭제

* vi 명령어
	x 한글자 삭제
	u 실행취소
	dd 한줄 삭제
	yy 한줄 복사
	p 붙여넣기
	w 저장 
	q 나가기
	q! 저장하지 않고 나가기
	
### git 기본 명령어
* git --version	
* git init 현재 있는 워킹 디렉토리에 로컬 repository 생성(.git^숨김폴더^디렉토리 생성)
* git status 현재 워킹 디렉토리 상태 확인
* git config 
	* --global user.email "aaa@aaa.com" 초기에 유저 설정
* git commit 하고나면 커밋메세지 작성 창이 나온다.
	* -m "메세지내용" 간단한 메세지로 커밋하기 
	* -a add없이 한번에 커밋하기 
* git log 히스토리 확인하기
	* -p 변경사항도 보여준다
	* --graph 트리그래프로 보여준다. 
* git diff 변경사항 보여줌 (레파지토리 안에서 해야한다.)	
	
* git add
	* -A 한꺼번에 스테이지로 올리기
* git reset HEAD 파일명 스테이지에서 내리기 - HEAD는 현재 브랜치의 stage area를 말한다.
* git clone
* git push
* git reset --mode
	* git reset --hard 커밋번호 특정 커밋상태로 되돌리기
* git revert 커밋번호 특정 커밋만 취소해준다. 이때의 변경사항만 사라진다.
* git branch 브랜치 확인하기
	* git branch 브랜치명 - 브랜치 생성 
	* git branch 파생브랜치 상위브랜치 - 파생되는 브랜치 생성
	* git branch -d 브랜치 삭제 
* git checkout 넘어갈 브랜치명 : 다른 브랜치로 넘어가기 
	* -b : 만들면서 동시에 넘어가기 
* git checkout 브랜치 바꾸기
* git merge 

### 실습
1. 터미널에서 ~/git/second_git 에 git init
2. index.html 만들기
3. git status로 확인하고 git add index.html 한다. 다시 git status로 상태확인하면 stage area로 올라간 것을 확인할 수 있다. 새로 만든 파일이므로 new file 이라고 뜸. 
4. git config 로 유저 설정후에 git commit index.html 하면 커밋메세지 쓰는 화면이 나온다. 
5. texts 디렉터리 만들구 index.html다시 수정후에 한꺼번에 add,commit 하기. (git add -A git reset HEAD )

### clone

### reset
git reset --hard 커밋번호
	HEAD가 특정 커밋위치로 이동한다. 
git reset --head ORIG_HEAD
	리셋한거 다시 취소하고 원래의 마지막 커밋 상태로 돌아가기. 
	
### revert
```
kizmo04@kizmo-laptop:~/git/first_git$ git revert fb5bd971a3e3d8d60454becb7f52f47dc9c97238
[master acbd756] Revert "make.txt생성"
 1 file changed, 5 deletions(-)
 delete mode 100644 make.txt

```

### remote repository 만들고 local push하기
git remote add origin https://github.com/kizmo04/second_git.git
git push -u origin master

```
kizmo04@kizmo-laptop:~/git/second_git$ git remote add origin https://github.com/kizmo04/second_git.git
kizmo04@kizmo-laptop:~/git/second_git$ git push -u origin master
Username for 'https://github.com': kizmo04
Password for 'https://kizmo04@github.com': 
Counting objects: 21, done.
Delta compression using up to 8 threads.
Compressing objects: 100% (15/15), done.
Writing objects: 100% (21/21), 2.14 KiB | 0 bytes/s, done.
Total 21 (delta 4), reused 0 (delta 0)
remote: Resolving deltas: 100% (4/4), done.
To https://github.com/kizmo04/second_git.git
 * [new branch]      master -> master
Branch master set up to track remote branch master from origin.

```

### gitignore
.gitignore 쓸 필요가 없거나 git에서 관리될 필요 없는 파일들을 여기에 명시해준다. 
> https://www.gitignore.io/ 에서 생성하면 편하다. 
> **git init 하자마자 해줘야 한다. (repository 생성과 동시에 해야 트래킹하지 않는다.)**
	각자 다른 setting환경에서 개발하기 때문에 발생하는 conflict 방지!!!
	처음 레포지토리 만드는 사람이 생성하고 이니셜 커밋을 해야함. 이 .gitignore를 collaborator들이 모두 같이 사용하기때문. 
	
	
## 순서
1. git init
2. .gitignore 생성 + README.md생성
3. initial commit
4. branch 분기

## branch 실습 (/html_example)
1. git init
2. .gitignore + git add + git commit(initila commit)
3. git branch html - html 브랜치 만들기
4. git branch css - css 브랜치 만들기
5. index.html 만들기 
6. git checkout html : html 브랜치로 넘어가기 
7. git add + git commit (index.html )
8. git checkout master 
9. master 브랜치에서 확인해보면 index.html 이 존재하지 않는다. (파일들이 브랜치마다 각자 관리된다)
10. 이번에는 html브랜치를 두갈래로 나눠본다. (하위 갈래 생성)
	git branch feature html 
	html에서 파생된 feature가 생겼다. html의 마지막 상태를 그대로 가지고 생겨난 브랜치다.
11. feature 브랜치도 commit을 해준다. 
12. git branch fix html 로 html에서 파생되는 다른 브랜치를 만들어주고 
13. fix 브랜치로 checkout 한 상태로 커밋해준다. 
14. html 브랜치로 merge를 해보기
	fix 브랜치의 로그에서 html에 반영할 커밋 번호를 저장
	html 브랜치로 checkout 한 상태에서 git merge 가져올커밋번호 
	fix브랜치의 내용이 html브랜치에 반영이 되었다. history도 가져온다. 
	
	
