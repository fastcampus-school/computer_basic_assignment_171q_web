* Git 사전 작업 (mac은 상관없음)
1. git config —global user.email “   “ : 사용자 메일 주소 등록
2. git config —global user.name “   “ : 사용자 이름 등록 —> git config —list : 설정 값 전부 확인 가능 —> git config user.name : 사용자 이름 확인 가능 —> git config user.email : 사용자 메일 확인 가능

* Git 실행 순서
1. git init  : Git 폴더로 사용할 폴더를 지정 해주는 과정 (하고싶은 폴더 안에서 실행)
2. git ignore : 이과정을 하지 않으면 사용자 개인 설정까지 pull이되서 conflict가 발생함 꼭 해줘야 하는과정 : ignore 할 파일을 전부다 담을 .gitignore(이름변경 불가능)파일을 만들어 준다(vi .gitignore 해주면됨) : 만들어준 txt파일 안에 ignore하고 싶은 파일이름을 전부다 적어준다 : 만들어준 파일 이름.gitignore 해준다 : 처음에 레파지토리 만들어주는 사람이 하는게 좋음 (모든 contiributer에게 적용이 되기 때문)
3. git add  : 변경 사항들을 staged 상태로 변경 해줌
    1. git add —all : 한번에 staged상태로 변경을 해줌
4. git commit  : staged상태로 변경된 것들을 commit 해주는 과정
    1. git -a -m “   “ : add 와 commit을 한번에 해줌
5. git push  : commit 이 된 것들을 push 해주는 과정 1. git remote add 리모트이름 원격저장소주소 (ex git remote add origin htpp://...) 2. git push -u 리모트이름 브랜치이름 (git push -u origin master) 3. git remote -v (저장해놓은 원격저장소 확인가능)
  —> 1,2번 과정은 한번만 해주면 됨, 3,4,5 과정은 반복 과정

* Git clone 하는 방법
1. clone을 받고 싶은 디렉토리로 이동
2. git clone 깃허브주소

* Git reset 하는 방법 (잘 사용하지 않음)
1. git reset —hard 커밋번호 : 커밋번호 시점으로 돌아감
2. git reset —hard ORIG_HEAD : 방금 리셋한거 취소 하고 싶을 경우 사용함(위에꺼 하고 바로 해야됨)

* Git revert 하는 방법 (잘 사용하지 않음, GUI 에서는 reverse 라고 표기됨)
1. git revert 커밋번호 : 해당 커밋에 해당 하는 것으로 돌려줌

* Branch 생성 하는 방법
1. Branch 생성 : git branch 이름 (git branch 로 확인가능, *표시는 현재 니가 있는 branch)
2. Branch 이동:  git checkout 이름 : checkout 을 하면 이동한 branch의 최근 commit 상태로 돌아간다 (폴더에서 확인가능) : -> 각자 노선에 해당하는 파일 들만 보여 준다는 뜻
3. 하위 브랜드 만드는 방법 : 독자 노선 탄 브랜치로 이동 후  -> git branch feature html : -> html이 미리 독자노선 타논 브랜치 feature 가 html브랜치에서 새로 독자노선을 탈 branch이다.

* Merge 하는 방법
1. git merge 커밋번호 (병합 결과 물이 있을 branch에서 실행해줘야 한다, 병합 대상의 커밋번호) -> 병합 대상 이 병합 결과물이 있을 branch로 합쳐 진다

* Branch Merger 추가 사항
1. branch 삭제방법 : git branch -d 브랜치 이름
2. branch 계층도 확인방법 : git log --graph --decorate --oneline —all

* 기타 Git 명령어
1. git log : history 확인
2. git status : 상태 확인

* 기타 Termial 명령어
1. cd .. : 상위 폴더로 이동
2. pwd : 현재 경로 표시
3. open . : 현재 경로 폴더 오픈
4. ls : 폴더 안에 있는 내용물 표시
5. mkdir 폴더명 : 폴더 생성 
6. rm 파일명 : 파일 살제
7. rm -rf  폴더명: 폴더 삭제



