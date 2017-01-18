**Comment: ctr+c/ctr+v는 지양합시다~**

# 버전관리
## 버전관리란
파일 변화를 시간에 따라 기록하는 것이다. *기록한 했던 것은(?????)* 나중에 특정 시점의 버전을 다시 꺼내 작업할 수 있다.

## 버전관리 방법
### 로컬 버전 관리
아주 간단한 데이터베이스를 사용해서 파일의 변경 정보를 관리한다. 많이 쓰는 도구는 RCS가 있다.

### 중앙집중식 버전관리
 CVS, Subversion, Perforce 같은 시스템은 파일을 관리하는 서버가 별도로 있고 클라이언트가 중앙 서버에서 파일을 받아서 사용(Checkout)한다. 그러나 이 환경은 몇 가지 치명적인 결점이 있다. 가장 대표적인 것이 중앙 서버에 발생한 문제다. 만약 서버가 한 시간 동안 다운되면 그동안 아무도 다른 사람과 협업할 수 없고 사람들이 하는 일을 백업할 방법도 없다. 그리고 중앙 데이터베이스가 있는 하드디스크에 문제가 생기면 프로젝트의 모든 히스토리를 잃는다.

### 분산 버전 관리 시스템
Git, Mecurial, Bazaar, Darcs 같은 DVCS에서의 클라이언트는 단순히 파일의 마지막 스냅샷을 Checkout 하지 않는다. 그냥 저장소를 전부 복제한다. 서버에 문제가 생기면 이 복제물로 다시 작업을 시작할 수 있다. 클라이언트 중에서 아무거나 골라도 서버를 복원할 수 있다. 모든 Checkout은 모든 데이터를 가진 진정한 백업이다.

게다가 대부분의 DVCS 환경에서는 리모트 저장소가 존재한다. 리모트 저장소가 많을 수도 있다. 그래서 사람들은 동시에 다양한 그룹과 다양한 방법으로 협업할 수 있다. 계층 모델 같은 중앙집중식 시스템으로는 할 수 없는 Workflow를 다양하게 사용할 수 있다.

# git 명령어
## init
현재 디렉토리를 git 버전 관리 디렉토리로 설정

```shell
$ git init
```

## status
레포지토리의 상태를 조회한다.

```shell
$ git status
```

## add
working directory 파일을 staging area에 추가
```shell
$ git add index.html
```

## commit
staging area의 파일들을 repository 영역으로 저장
```shell
$ git commit
$ git commit -m "Add about.html"

# add 없이 commit
$ git commit -a -m "Add html tag"
```

## log
repository의 commit 이력을 조회

``` shell
$ git log
$ git log --oneline
$ git log --oneline --decorate --graph --all
# 특정 파일의 로그 조회
$ git log -- index.html
```

## diff
현재 브랜치의 마지막 커밋과 working directory를 비교
```shell
$ git diff
$ git diff -- index.html
```

## branch
브랜치를 생성, 수정, 삭제
```shell
# develop 브랜치 생성
$ git branch develop

# 브랜치 목록 조회
$ git branch

# develop 브랜치로 변경
$ git checkout develop

# develop 브랜치 삭제
$ git branch -d develop

# develop 브랜치를 test 브랜치로 변경
$ git branch -m develop test

# 원격 브랜치까지 조회
$ git branch -a
```

## Checkout
두 개의 브랜치를 병합하거나 특정 커밋을 현재 브랜치에 병합
```shell
# develop 브랜치를 master 브랜치에 병합
$ git merge develop
```
