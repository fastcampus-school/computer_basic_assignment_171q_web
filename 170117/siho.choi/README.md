최시호 숙제

#git 명령어

##git --version
현재 git의 버전을 확인. git이 깔려있는지 확인

##git init
현재 워킹 디렉토리에 .git 폴더 생성

## git add 파일이름
파일을 스테이지에 올리기
스테이지에서 뺄 때는 `$ git reset 파일이름`
다 올릴 때는 `$ git add -all`

## git status
현재 워킹 디렉토리 상태 확인
커밋되지 않은 변경사항 조회

## git commit
git 설정이 되어 있지 않으면 `git config` 진행 (화면에 나타난대로 진행하면 됨)
vi로 진입하여 commit message 입력하고 저장하면 commit 완료

## git commit -m "커밋메시지"
한 줄로 간단하게 커밋

## git diff
마지막 커밋과 워킹디렉토리 차이를 보여줌

## git log
히스토리 조회
리포지토리 커밋 이력 조회
`$ git log -p` 어떤 파일이 수정되었는지까지 확인
`$ git log --graph`그래프도 같이 보기

## git reset --hard 커밋번호
커밋번호로 리셋 (여기서 커밋번호는 리셋하여 돌아갈 커밋번호를 적는다. `git log`를 통해 확인

## git reset --hard ORIG_HEAD
방금 리셋한거 취소하고 다시 원상복구 

## git revert 커밋번호
커밋번호를 그 전으로 되돌린다. (여기서 커밋번호는 되돌릴 대상의 커밋번호를 적는다. reset 할때 커밋번호와 다름 주의!)

## git pull
git pull 리모트-리포지토리-네임 origin master
리모트-리포티토리-네임 = github 에 있는 remote repository name
clone 한 다음에 다른 사람이 작업했을 경우 push 가 안될 수 있다. 이 때는 다시 git pull origin master 로 pull 한다.

## git clone 리모트-리포지토리-네임 내-디렉토리
내-디렉토리 에 리모트-리포지토리-네임 을 클로닝

## github 에 새 리포지토리 만들고 내 워킹디렉토리와 연결하는 법
```
$ git remote add origin 리모트-리포지토리-네임
$ git push -u origin master
```

## git init 하자마자 .gitignore 만들어 주자
http://gitignore.io 사이트 가서 OS, 각종 사용 Application 을 선택하고 간편하게 generate!!
.gitignore 파일도 커밋하고 푸시까지
