##Version Control System (VCS)
(예) git, subversion(주의: 절대 쓰지 말 것), mercurial(가끔 쓰임)

* 타임머신 백업 : 시간별로 저장을 해서 특정시점의 버젼을 불러올 수 있다.
* Branch(분기)를 이용한 병렬 관리
* 공유

##Git
1. Working Directory : 작업이 이루어지는 로컬폴더/파일
2. Staging Area : 작업 후 git 저장 전 대기 로컬 가상공간 (명령어로 싱크할 파일을 고른다.)
	* add : staging area에 추가
	* unstage : staging area에서 제거
	* gitignore : 이 파일에 적은 내용은 자동으로 배제된다.
3. Repository (.git directory) : git 저장소 (로컬, 리모트) 히스토리를 남기기 때문에 되돌릴 수가 없다. 되돌릴 수는 있는데 되돌렸다는 기록이 남는다. 그리고 되돌리기 전 기록도 남아있다. 결국 못 되돌린다.
	* commit : local repository로 보내기
	* push : local에서 remote repository로 보내기
	* pull : remote repository에서 working directory로 가져오기

`[working directory] -- add --> [stage area] -- commit --> [local repository] -- push --> [remote repository]`
`[remote repository] -- fetch --> [local repository] -- merge --> [working directory]`
`[remote repository] -- pull --> [working directory]`

###commit
적당한 commit 단위를 잡아놓을 것.  
통상 하나의 작업 단위를 사용한다.
####reverse commit
취소

###reset
특정시점으로 작업을 되돌린다.
* soft : local repository에 저장된 작업물까지
* mixed : staging area에 저장된 작업물까지
* hard : working directory의 작업물까지 `**주의 : 히스토리까지 지워버리기 때문에 복구불가능하다!`

###branch
따로 실험적으로 돌려보고 싶을 때 만든다.  
그냥 원래 있던 master를 복사한 후 쓰다가 다시 merge해버리면 됨.

###merge
branch에서 가져와서 합체.  
merge conflict가 나올 가능성이 매우 높으므로 항상 수정작업을 시행할 것.

#Terminal
###command line
* clear : terminal 화면을 첫줄로 하기
* c - : 명령어 c에 대한 옵션기능
	* c -help : 명령어 c에 대한 도움말
		* c --help : 다른 창 도움말에 열기 (q로 닫기)
* pwd : 현위치
* cd F : change directory 폴더 F로 이동
	* cd F/G/H : F의 하위폴더 G의 하위폴더 H로 이동
* ~ : home directory
	* cd ~ : home directory로 이동
* .. : 상위폴더
	* cd .. : 상위폴더로 이동
* open . : 현재폴더 열기
* ls : list 폴더 안 파일 목록
	* ls -a : 숨김 파일 포함 목록
* mkdir F : make directory 폴더 F 생성
* vi f : 파일 f 생성 혹은 열기 (확장자까지 쓸 것)
	* vi .gitignore : gitignore를 만든다. 이 안에 저장해둔 것들은 git이 무시한다. 반드시 git init을 하고 바로 하는 것이 좋다. gitignore.io 사이트를 활용한다.
	* i : insert 편집 모드
	* esc : 모드 취소
	* u : 실행 취소
	* x : 한글자 삭제
	* yy : 한 줄 복사
	* p : 붙여넣기
	* : : 명령어
		* :w : 저장
		* :q : 닫기
		* :q! : 강제닫기
		* :wq : 저장 후 닫기
* rm f : remove 파일 f 완전삭제 (복구불가)
	* rm -rf F : 폴더 F 완전삭제 (복구불가)

##git
###command line
* git init : 현폴더를 git local repository로 설정
* vi .gitignore : gitignore 파일 생성 (반드시 git init 직후에 해주도록 함)
* git branch : local repository의 branch 확인
* git branch b : branch b 생성
* git branch b B : branch B 하위 branch b 생성
* git branch -d b : branch b 삭제
* git checkout b : branch b로 이동
	* git checkout -b b : branch b를 생성 후 이동
* git status : 현 local repository의 상태 확인
* git add f: 파일 f를 staging area로 add
	* git add -A : 폴더 아래 모든 파일을 add
* git reset HEAD f: 파일 f를 unstage
* git commit : staging area의 파일을 commit
	* git commit f : 파일 f를 add하고 commit
	* git commit -m "t": message t를 써서 commit
	* git commit -a : 폴더 아래 모든 파일을 add하고 commit
* git push : push
* git revert n : commit 번호 n을 reverse commit하기
* git reset --m n : commit 번호 n으로 m 모드(soft, mixed, hard)를 이용해 되돌리기
* git reset --m ORIG_HEAD : reset 취소로 마지막 commit 상태로 되돌리기 (단, 다른 행동을 하면 되돌릴 수 없음)
* git merge n : commit 번호 n을 현 branch에 merge
* git clone url : url의 git을 현폴더에 복사
* git log : history 확인

###git terminal procedure
> create local directory

1. `cd` 폴더를 만들 위치로 이동
2. `mkdir` 폴더 생성
3. `cd` 폴더 열기

> set local repository

1. `git init` 폴더를 local repository로 설정

> commence initial commit

1. `vi .gitignore` 예외 목록 파일 작성
2. `git add -A` 파일을 staging area에 등록
3. `git commit` 파일을 local repository에 등록

> create and switch branch

1. `git branch` branch 생성
2. `git checkout` branch 변경

or

1. `git checkout -b` branch 생성 후 변경

> merge

1. `git checkout` merge에 쓸 파일을 가진 branch로 이동
2. `git log` 히스토리에서 commit 번호 확인
3. `git checkout` merge할 branch로 이동
4. `git merge` merge 실행

> solve merge conflict

1. `git checkout` merge conflict가 일어난 branch로 이동
2. `vi` merge conflict가 일어난 파일 수정
3. `git add` 파일 add
4. `git commit` 파일 commit

> update branch

1. `git checkout` merge conflict를 해결한 branch로 이동
2. `git log` 히스토리에서 merge conflict를 수정한 commit 번호를 확인
3. `git checkout` 업데이트할 branch로 이동
4. `git merge` merge해서 덮어쓰기

> set remote repository

1. `git remote add origin` url을 따와서 remote repository를 추가

> push

1. `git push --all` 전부 push 실행