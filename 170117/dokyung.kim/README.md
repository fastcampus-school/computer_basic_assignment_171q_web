**Comment: ctr+c/ctr+v는 지양합시다~**


# 2017-01-17

##버전 관리란 ?
>
**버전 관리(version control, revision control)**, 소스 관리(source control), 소스 코드 관리(source code management, SCM)란 **동일한 정보**에 대한 **여러 버전을 관리하는 것**을 말한다. 
- [위키백과](https://ko.wikipedia.org/wiki/%EB%B2%84%EC%A0%84_%EA%B4%80%EB%A6%AC)
>
버전(version)은 변경된 이력을 의미한다. 현실에서도 기능이 개선되었다는 의미로 버전업이라는 말을 많이 쓴다는 것을 상기해보자. 버전관리 시스템은 코드의 변화를 관리하는 시스템이다. 각각의 변화들을 저장해서 현재 코드의 상태가 어떤 맥락을 거쳐서 지금의 상태가 되었는지를 파악하고, **문제가 생겼을 때 과거로 돌리는 등의 기능**을 제공한다. 특히 코드라는 중요한 데이터를 안전하게 보관한다는 의미에서 백업의 기능도 하게 된다. 또, **여러 사람이 협업을 할 때 발생할 수 있는 충돌이나 유실을 방지하는 역할**도 휼룡하게 수행한다. 버전관리는 프로그래밍에 있어서 빼놓을 수 없는 체계로 자리 잡고 있다.
- [생활코딩](https://opentutorials.org/course/488/2605)

###사용해야하는 이유
>
- 소스 백업이 편하다.  
- 빌드 후 버그 발생 시 빌드 이전 소스로 복구가 편하다.  
- 다수 작업자 혹은 다른 장소에서의 소스 동기화가 편하다.  
- 동일 소스에서 동시에 다른 프로젝트가 진행 될때 소스 병합이 편하다.  
- 어느 시점에 누가 무슨 이유로 소스를 변경했는지 확인이 편하다

## 버전관리방법

- **로컬 버전 관리 시스템 (Local VCS)**  

> 
 간단한 데이터베이스를 사용하여 파일의 변경 정보를 관리한다.
>
 RCS : 기본적으로 Patch Set(파일에서 변경되는 부분)을 관리한다.
>
![](http://git-scm.com/figures/18333fig0101-tn.png)

- **중앙집중식 버전 관리 시스템 (Centralized VCS - CVCS)**

>
 프로젝트를 진행할 때 다른 개발자와 함께 작업해야하는 경우 사용되는 시스템이다.  
파일을 관리하는 서버가 별도로 있고 클라이언트가 중앙 서버에서 파일을 받아(Checkout) 사용할 수 있다.  
>
 CVCS : 관리자가 프로젝트에 참여한 사람 중 누가 무엇을 하는지 관리하기 쉽다. 하지만 중앙 서버에 문제가 발생하여 다운될 경우, 그동안에는 협업 및 백업이 불가능하다. 또한 하드디스크에 문제가 생긴다면 프로젝트의 모든 히스토리를 잃을 수도 있다.  
> 
![](http://git-scm.com/figures/18333fig0102-tn.png)

- **분산 버전 관리 시스템 (Distributed VCS - DVCS)**

> 클라이언트가 파일의 마지막 스냅샷을 가져오는 것이 아니라 저장소 자체를 복제하게 된다.  
>  서버에 문제가 생길 경우 이 복제물로 작업이 가능하며 서버를 복원할 수도 있다.  
>  또한 리모트 저장소가 존재하며 리모트 저장소가 많을 수도 있다.  
>  즉, 동시에 다양한 그룹과 다양한 방법으로 협업이 가능하다.  
> 
![](http://git-scm.com/figures/18333fig0103-tn.png)

-
## Git Commnd

- `git --version` : Git 버전 확인  
- `git init` : Local Repo 생성  
- `ls - a` : (숨김 폴더 유무확인으로 생성확인)  
- `git -help` : 도움말  
- `git status` : working directory 디렉토리 상태 확인
- `git add 파일명` : 변경된 파일을 working directory에서  stage area으로 올리기  
- `git add -A` : 변경된 파일 모두를 working directory에서  stage area으로 올리기  
- `git commit` : stage area에 올라온 파일을 local repository에 올리기 + comment 남기기  
- `git commit --help` : commit 도움말  
- `q` : 나가기  
- `git commit -m "내용"` : commit message도 명령어로 한번에 처리  
- `git commit -a -m`: stage와 올라가는 동시에 commit도 진행 (처음 생성한 파일은 안됨)  
**명령어들 사이에 띄어쓰기 중요!**  
- `git log` : 히스토리 보기  
- `git log -p` : 로그상에서 수정부분 간단히 확인.
- `git reset HEAD 파일명` : 리셋
- `git clone 주소` : Local repository에 git이 없거나 삭제했을때 remote repository에서 복구  
- `git diff 파일명` : 커밋전까지 변경부분 조회
- `git push` : Local repository에 commit한 파일 및 내용들을 remote repository으로 push
- `git reset --hard HEAD--`, `git reset --hard 커밋번호`, `git reset --hard ORIG_HEAD` : 리셋도 취소할 수 있음 (커밋이 있으면 안됨)  
- `git revert 커밋번호` : 특정 commit 작업을 취소

### Remote
1. `git remote add origin 깃주소`
2. `git push -u origin master`

#중요!!!!
**`vi .gitignore`**  
> Git에서 관리하지 않을 파일 리스트를 작성  
[gitignore.io](https://www.gitignore.io) 에서 목록 받아와서 작성.  
(git init하자마자 진행할 작업)

### Branch

- `git branch 브렌치이름` : 브렌치 생성
(ex: git branch html)  
- `git checkout 브렌치이름` : 브렌치이동, -b 옵션은 생성시 바로 이동
- `git branch 생성할 브렌치 이름 / 상위 브렌치` : 하위 브렌치 생성
- `git branch -d 브랜치명 `: 브렌치 삭제

### merge
merge할 branch로 checkout 후  
`git merge 커밋번호`

-
처음 Git 생성시 작업 순서

1. `init`
2. `gitignore`
3. `git status`
4. `git add -A`
5. `git commit` (initial commit)
(브렌치 생성)  
6. `git branch 브렌치이름` (ex: git branch html)
7. `git checkout 브렌치이름` (브렌치이동, -b 옵션은 생성시 바로 이동)
8. `git add - git commit`
9. `git branch 생성할 브렌치 이름 / 상위 브렌치` : 하위 브렌치 생성

##### Vim 단축키 참고
`u` 되돌리기  
`x` 한글자 되돌리기  
`yy` 한줄복사  
`p` 붙여넣기
