#버전 관리 정리!

##버전 관리란?

버전 관리 시스템은 파일의 변화를 시간에 따라 기록하여 과거 특정 시점의 버전을 다시 불러올 수 있는 시스템이다.

* 로컬 버전 관리 시스템!

대부분의 사람들이 버전 관리를 위해 쓰는 방법은 파일을 다른 디렉토리에 복사하는 것이다.(디렉토리 이름에 시간을 넣어주는게 현명하다.)
이 방법은 간단하고 자주 사용되는 방법이지만 실수가 발생하기 쉽다.
어느 디렉토리에서 작업하고 있었는지 잊어버리고 엉뚱한 파일을 덮어쓰거나 의도하지 않았던 위치로 복사할 수도 있다.

이 문제를 해결하기 위해 오래전에 프로그래머들은 간단한 데이터베이스에 파일의 변경 사항을 기록하는 로컬 버전 관리 시스템을 만들었다!

* 중앙집중식 버전 관리 시스템

또 다른 문제는 시스템 외부에 있는 개발자들과 함께 작업하는 것이다. 중앙집중식 버전 관리 시스템은 이 문제를 해결하기 위해 개발됐다.
CVS,Subversion,Perforce 와 같은 시스템들이 여기에 속한다. CVCS에서는 버전 관리되는 모든 파일을 저장하는 하나의 서버와, 이 중앙 서버에서 파일들을 가져오는 다수의 클라이언트가 존재한다.
오랫동안 사용된 이 방식은 지금까지도 버전 관리의 대표적인 방식이다.

* 분산 버전 관리 시스템

분산 버전 관리 시스템은 앞서 말한 문제를 해결하기 위해 개발 되었다. Git,Mecurial,Bazaar,Darcs 등 DVCS에서는 클라이언트가 파일들의 마지막 스냅샷을 가져오는 대신 저장소를 통째로 복제한다.
따라서 서버에 문제가 생겨도 어느 클라이언트든 복제된 저장소를 다시 서버로 복사하면 서버가 복구된다.
체크아웃(checkout)을 할 때마다 전체 백업이 일어나는 셈이다

#git 명령어 정리!

##git --version

* 현재 git의 버전을 확인합니다.

##git init

* 현재 디렉토리에 git 저장소를 생성합니다.

##git add

* git add [파일] : stage area에 파일을 추가하여 commit 할 수 있도록 한다.

##git commit

* git commit -m”mention” : stage area에 있는 파일들을 commit 한다.
* git commit -a -m”mention” : 이미 추가된 파일이 수정 중인 상황에서 stage area에 올리지 않아도 stage area에 올리고 바로 commit 한다.

##git remote

* git remote add [저장소] [저장소주소] : 원격 저장소를 추가한다.
* git remote -v : 원격 저장소 목록을 보여준다.

##git clone

* git clone [주소] [저장될 폴더] : git 원격 저장소에 있는 프로젝트를 내려받는다.
* git clone –depth [숫자] [주소] : 프로젝트가 많은 커밋들을 가지고 있을 경우 내려받는데 오래 걸리므로 depth 옵션을 사용하면 해당 숫자만큼의 최신 커밋들만 가지고 프로젝트를 내려받는다.

##git push

* git push origin master : origin 원격 저장소에 master 브랜치에 추가된 스냅샷들을 올린다.
* git push origin +master : origin 원격 저장소에 master 브랜치에 추가된 스냅샷들을 강제로 올린다.

##git stash

* git stash : 변경된 내역들을 스택에 만들고 워킹디렉토리는 깨끗하게 비운다.
* git stash list : 스택에 저장된 내역들을 확인할 수 있다.
* git stash apply : 스택에 저장된 최신의 stash를 적용한다.
* git stash apply stash이름(ex.stash@{0}) : 스택에 저장된 stash중 이름이 같은 stash를 적용한다.
* git stash apply –index : Stage 상태로 스택에 저장된 stash를 Stage 상태까지 복원한다.

##git tag

* git tag : 만들어진 태그 목록을 보여준다.
* git tag [태그] : 태그를 만든다.
* git tag -l ‘v1.0′ : 1.0버전의 태그들만 검색하여 보여준다.

##git diff

* git diff : 파일 변경사항들을 보여준다.
* git diff [파일] : 해당 파일의 변경사항을 보여준다.

##git branch

* git branch : 브랜치 목록을 보여준다.
* git branch [브랜치] : 브랜치를 생성한다.

##git checkout

* git checkout [브랜치] : 해당 브랜치로 이동한다. - git checkout -b [브랜치] : 브랜치가 없으면 브랜치를 생성하고 이동한다.

##git merge

* git merge [브랜치] : 현재 브랜치에서 입력한 브랜치와 합친다.

##git reset

* git reset [커밋] [파일] : stage area에 있는 파일들을 모두 특정 커밋으로 되돌린다.
* git reset --soft 커밋 : 수정사항을 유지하고 특정 커밋으로 되돌린다.
* git reset --hard 커밋 : 수정사항을 무시하고 특정 커밋으로 되돌린다.



