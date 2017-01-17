# 2일차 과제 by 최영민 
####Index
####1. 버전관리란 무엇인가?
####2.버전관리 방법에는 어떤 것들이 있는지 알아보기
####3. git 명령어(command) 상세설명 
####4. git 명령어 핵심 정리 
--- 
####1. 버전관리란 무엇인가? 

버전 관리 시스템은 파일의 변화를 시간에 따라 기록하여 과거 특정 시점의 버전을 다시 불러올 수 있는 시스템이다. 이 책에는 소프트웨어의 소스 코드를 버전 관리하는 예만 나오지만 실제로는  **모든 컴퓨터 파일이 버전 관리의 대상**이 될 수 있다.

이미지나 레이아웃을 수정할 때마다 각각의 형태를 모두 보존하고 싶은 그래픽 디자이너나 웹 디자이너라면 **버전 관리 시스템(Version Control System; VCS)**을 사용하는 것이 현명할 수 있다. VCS를 사용하면 

- 개별 파일 혹은 프로젝트 전체를 이전 상태로 되돌리거나 
- 시간에 따른 변경 사항을 검토할 수 있으며, 
- 문제가 되는 부분을 누가 마지막으로 수정했는지, 
- 누가 언제 이슈를 만들어냈는지 등을 알 수 있다. 
- 또한 파일을 잃어버리거나 무언가 잘못되어도 대개 쉽게 복구할 수 있다. 
- **그리고 이 모든 장점을 누리는 데는 큰 노력이 들지 않는다.**

---
####2.버전관리 방법에는 어떤 것들이 있는지 알아보기

<span style="color: tomato; font-size:18px">로컬 버전 관리 시스템<span>

대부분의 사람들이 버전 관리를 위해 쓰는 방법은 파일을 다른 디렉토리에 복사하는 것이다(똑똑한 사람이라면 디렉토리 이름에 시간을 넣을 것이다). 이 방법은 간단하고 자주 사용되는 방법이지만 실수가 발생하기 쉽다. 어느 디렉토리에서 작업하고 있었는지 잊어버리고 엉뚱한 파일을 덮어쓰거나 의도하지 않았던 위치로 복사할 수도 있다.

이 문제를 해결하기 위해 오래전에 프로그래머들은 간단한 데이터베이스에 파일의 변경 사항을 기록하는 로컬 버전 관리 시스템을 만들었다(그림 1-1 참조).
![img](https://git-scm.com/figures/18333fig0101-tn.png)
그림 1-1. 로컬 버전 관리 다이어그램
유명했던 VCS 도구들 중 현재에도 널리 쓰이는 것으로 RCS라 불리는 시스템이 있다. 그 예로 Mac OS X 운영체제에서는 개발 도구를 설치하면 RCS가 딸려온다. RCS의 기본적인 동작 방식은 각 리비전들 간의 패치 세트(patch set)라고 하는 데이터의 차이점들을 특별한 형식의 파일에 저장, 특정 시점의 파일 내용을 보고 싶을 때 해당 시점까지의 패치들을 모두 더하여 파일을 만들어내는 것이다.

<span style="color: tomato; font-size:18px">중앙집중식 버전 관리 시스템<span>

또 다른 문제는 시스템 외부에 있는 개발자들과 함께 작업하는 것이다. 중앙집중식 버전 관리 시스템(Centralized Version Control System; CVCS)은 이 문제를 해결하기 위해 개발됐다. CVS, Subversion, Perforce와 같은 시스템들이 여기에 속한다. CVCS에서는 버전 관리되는 모든 파일을 저장하는 하나의 서버와, 이 중앙 서버에서 파일들을 가져오는(checkout) 다수의 클라이언트가 존재한다. 오랫동안 사용된 이 방식은 지금까지도 버전 관리의 대표적인 방식이다(그림 1-2 참조).

![img](https://git-scm.com/figures/18333fig0102-tn.png)

그림 1-2. 중앙집중식 버전 관리 다이어그램
CVCS는 로컬 VCS에 비해 장점이 많다. 누구나 다른 사람들이 무엇을 하고 있는지 알 수 있고, 관리자는 누가 무엇을 할 수 있는지 꼼꼼하게 관리할 수 있다. CVCS를 관리하는 것은 수많은 클라이언트의 로컬 데이터베이스를 관리하는 것보다 훨씬 쉽다.

그러나 CVCS는 심각한 단점이 있다. 중앙 서버가 잘못되면 모든 것이 잘못된다는 점이다. 서버가 다운될 경우 서버가 다시 복구될 때까지 다른 사람과의 협업도, 진행 중이던 작업을 버전 관리하는 것도 불가능해진다. 중앙 데이터베이스가 저장된 하드디스크에 오류가 발생하고 백업도 없다면, 사람들이 각자 자신의 컴퓨터에 가지고 있던 스냅샷 외에는 그동안 쌓인 프로젝트의 이력을 모두 잃게 된다. 로컬 VCS 시스템도 같은 문제가 있다. 프로젝트의 모든 이력이 한곳에만 있을 경우 이것은 피할 수 없는 문제다.

<span style="color: tomato; font-size:18px">분산 버전 관리 시스템<span>

분산 버전 관리 시스템(Distributed Version Control System; DVCS)은 앞서 말한 문제를 해결하기 위해 개발되었다. Git, Mecurial, Bazaar, Darcs 등 DVCS에서는 클라이언트가 파일들의 마지막 스냅샷을 가져오는 대신 저장소(repository)를 통째로 복제한다. 따라서 서버에 문제가 생겨도 어느 클라이언트든 복제된 저장소를 다시 서버로 복사하면 서버가 복구된다. 체크아웃(checkout)을 할 때마다 전체 백업이 일어나는 셈이다(그림 1-3 참조).

![img](https://git-scm.com/figures/18333fig0103-tn.png)

그림 1-3. 분산 버전 관리 시스템 다이어그램
게다가 대부분의 DVCS에서는 다수의 원격 저장소(remote repository)를 갖는 것이 가능하기 때문에 동시에 여러 그룹과 여러 방법으로 함께 작업할 수 있다. 이로 인해 계층 모델(hierarchical model) 등 중앙집중 시스템에서는 할 수 없는 다양한 작업 방식(workflow)들을 사용해볼 수 있다.

---
여기서 잠깐, 
Git 명령어 이전에 GIt에 관해서 더 알아보는 시간을 가지자! 

<span style="color: tomato; font-size:18px">Git 기초<span>

Git의 핵심은 뭘까? 이 질문은 Git을 이해하는데 굉장히 중요하다. Git이 무엇이고 어떻게 동작하는지 이해한다면 쉽게 Git을 효과적으로 사용할 수 있다. Git을 배우려면 Subversion이나 Perforce 같은 다른 VCS를 사용하던 경험을 지워버려야 한다. Git은 미묘하게 달라서 다른 VCS에서 쓰던 개념으로는 헷갈릴 거다. 사용자 인터페이스는 매우 비슷하지만, 정보를 취급하는 방식이 다르다. 이런 차이점을 이해하면 Git을 사용하는 것이 어렵지 않다.

**델타가 아니라 스냅샷**
**Subversion과 Subversion 비슷한 놈들과 Git의 가장 큰 차이점은 데이터를 다루는 방법**에 있다. 큰 틀에서 봤을 때 대부분의 VCS 시스템이 관리하는 정보는 파일들의 목록이다. CVS, Subversion, Perforce, Bazaar 등의 시스템은 파일의 집합으로 정보를 관리한다. 각 파일의 변화를 그림 1-4처럼 시간순으로 관리한다.

![img](https://git-scm.com/figures/18333fig0104-tn.png)

그림 1-4. 각 파일에 대한 변화(델타)를 저장하는 시스템들
Git은 이런 식으로 데이터를 저장하지도 취급하지도 않는다. 대신 Git의 데이터는 파일 시스템의 스냅샷이라 할 수 있으며 크기가 아주 작다. Git은 커밋하거나 프로젝트의 상태를 저장할 때마다 파일이 존재하는 그 순간을 중요하게 여긴다. 파일이 달라지지 않았으면 Git은 성능을 위해서 파일을 저장하지 않는다. 단지 이전 상태의 파일에 대한 링크만 저장한다. Git은 그림 1-5처럼 동작한다.

![img](https://git-scm.com/figures/18333fig0105-tn.png)

그림 1-5. Git은 시간순으로 프로젝트의 스냅샷을 저장한다
이것이 Git이 다른 VCS와 구분되는 점이다. 이점 때문에 Git는 다른 시스템들이 과거로부터 답습해왔던 버전 컨트롤의 개념과 다르다는 것이고 많은 부분을 새로운 관점에서 바라본다. Git은 강력한 도구를 지원하는 작은 파일시스템이다. Git은 단순한 VCS가 아니다. 이제 3장에서 설명할 Git 브랜치를 사용하면 얻게 되는 이득이 무엇인지 설명한다.

**거의 모든 명령을 로컬에서 실행**
거의 모든 명령이 로컬 파일과 데이터만 사용하기 때문에 네트워크에 있는 다른 컴퓨터는 필요 없다. 대부분의 명령어가 네트워크의 속도에 영향을 받는 CVCS에 익숙하다면 Git이 매우 놀라울 것이다. Git의 이런 특징에서 나오는 미칠듯한 속도는 오직 Git느님만이 구사할 수 있는 초인적인 능력이다. 프로젝트의 모든 히스토리가 로컬 디스크에 있기 때문에 모든 명령을 순식간에 실행된다.

예를 들어 Git은 프로젝트의 히스토리를 조회할 때 서버 없이 조회한다. 그냥 로컬 데이터베이스에서 히스토리를 읽어서 보여 준다. 그래서 눈 깜짝할 사이에 히스토리를 조회할 수 있다. 어떤 파일의 현재 버전과 한 달 전의 상태를 비교해보고 싶을 때도 Git은 그냥 한 달 전의 파일과 지금의 파일을 로컬에서 찾는다. 파일을 비교하기 위해 리모트에 있는 서버에 접근하고 나서 예전 버전을 가져올 필요가 없다.

즉 오프라인 상태에서도 비교할 수 있다. 비행기나 기차 등에서 작업하고 네트워크에 접속하고 있지 않아도 커밋할 수 있다. 다른 VCS 시스템에서는 불가능한 일이다. Perforce는 서버에 연결할 수 없을 때 할 수 있는 일이 별로 없다. Subversion이나 CVS에서도 마찬가지다. 데이터베이스에 접근할 수 없어서 파일을 편집할 수는 있지만, 커밋할 수 없다. 매우 사소해 보이지만 실제로 이 상황에 부닥쳐보면 느껴지는 차이가 매우 크다.

**Git의 무결성**
Git은 모든 데이터를 저장하기 전에 체크섬(또는 해시)을 구하고 그 체크섬으로 데이터를 관리한다. 체크섬 없이 어떠한 파일이나 디렉토리도 변경할 수 없다. 체크섬은 Git에서 사용하는 가장 기본적인(Atomic) 데이터 단위이자 Git의 기본 철학이다. Git 없이는 체크섬을 다룰 수 없어서 파일의 상태도 알 수 없고 심지어 데이터를 잃어버릴 수도 없다.

Git은 SHA-1 해시를 사용하여 체크섬을 만든다. 만든 체크섬은 40자 길이의 16진수 문자열이다. 파일의 내용이나 디렉토리 구조를 이용하여 체크섬을 구한다. SHA-1은 아래처럼 생겼다:

24b9da6552252987aa493b52f8696cd6d3b00373
Git은 모든 것을 해시로 식별하기 때문에 이런 값은 여기저기서 보인다. 실제로 Git은 파일을 이름으로 저장하지 않고 해당 파일의 해시로 저장한다.

Git은 데이터를 추가할 뿐
Git으로 무얼 하든 데이터를 추가한다. 되돌리거나 데이터를 삭제할 방법이 없다. 다른 VCS처럼 Git도 커밋하지 않으면 변경사항을 잃어버릴 수 있다. 하지만, 일단 스냅샷을 커밋하고 나면 데이터를 잃어버리기 어렵다.

Git을 사용하면 프로젝트가 심각하게 망가질 걱정 없이 매우 즐겁게 여러 가지 실험을 해 볼 수 있다. 9장을 보면 Git이 데이터를 어떻게 저장하고 손실을 어떻게 복구해야 할지 알 수 있다.

세 가지 상태
이 부분은 중요하기에 집중해서 읽어야 한다. Git을 공부하기 위해 반드시 짚고 넘어가야 할 부분이다. Git은 파일을 Committed, Modified, Staged 이렇게 세 가지 상태로 관리한다. Committed란 데이터가 로컬 데이터베이스에 안전하게 저장됐다는 것을 의미한다. Modified는 수정한 파일을 아직 로컬 데이터베이스에 커밋하지 않은 것을 말한다. Staged란 현재 수정한 파일을 곧 커밋할 것이라고 표시한 상태를 의미한다.

이 세 가지 상태는 Git 프로젝트의 세 가지 단계와 연결돼 있다. Git 디렉토리, 워킹 디렉토리, Staging Area 이렇게 세 가지 단계를 이해하고 넘어가자.

![img](https://git-scm.com/figures/18333fig0106-tn.png)

그림 1-6. 워킹 디렉토리, Staging Area, Git 디렉토리
Git 디렉토리는 Git이 프로젝트의 메타데이터와 객체 데이터베이스를 저장하는 곳을 말한다. Git 디렉토리가 Git의 핵심이다. 다른 컴퓨터에 있는 저장소를 Clone 할 때 Git 디렉토리가 만들어진다.

워킹 디렉토리는 프로젝트의 특정 버전을 Checkout한 것이다. Git 디렉토리는 지금 작업하는 디스크에 있고 그 디렉토리에 압축된 데이터베이스에서 파일을 가져와서 워킹 디렉토리를 만든다.

Staging Area는 Git 디렉토리에 있다. 단순한 파일이고 곧 커밋할 파일에 대한 정보를 저장한다. 종종 인덱스라고 불리기도 하지만, Staging Area라는 명칭이 표준이 되어가고 있다.

Git으로 하는 일은 기본적으로 아래와 같다:

워킹 디렉토리에서 파일을 수정한다.
Staging Area에 파일을 Stage해서 커밋할 스냅샷을 만든다.
Staging Area에 있는 파일들을 커밋해서 Git 디렉토리에 영구적인 스냅샷으로 저장한다.
Git 디렉토리에 있는 파일들은 Committed 상태이다. 파일을 수정하고 Staging Area에 추가했다면 Staged이다. 그리고 Checkout하고 나서 수정했지만, 아직 Staging Area에 추가하지 않았으면 Modified이다. 2장에서 이 상태에 대해 좀 더 자세히 배운다. 특히 Staging Area를 어떻게 이용하는지 혹은 아예 생략하는 방법도 설명한다.



---
####3. git 명령어(command) 정리하기

<span style="color: tomato; font-size:18px">Git 저장소 만들기<span>

Git 저장소를 만드는 방법은 두 가지다. 1)기존 프로젝트를 Git 저장소로 만드는 방법이 있고 2)다른 서버에 있는 저장소를 Clone하는 방법이 있다.

####기존 디렉토리를 Git 저장소로 만들기

**기존 프로젝트를 Git으로 관리하고 싶을 때,** 프로젝트의 디렉토리로 이동해서 아래과 같은 명령을 실행한다.
```
$ git init
```
이 명령은 .git이라는 하위 디렉토리를 만든다. .git 디렉토리에는 저장소에 필요한 뼈대 파일(Skeleton)이 들어 있다. 이 명령만으로는 아직 프로젝트의 어떤 파일도 관리하지 않는다.

**Git이 파일을 관리하게 하려면 저장소에 파일을 추가하고 커밋해야 한다.** git add 명령으로 파일을 추가하고 커밋한다:
```
$ git add *.c
$ git add README
$ git commit -m 'initial project version'
```
매우 짧은 시간에 명령어를 몇개 실행해서 Git 저장소를 만들고 파일이 관리되게 했다.

####기존 저장소를 Clone하기

다른 프로젝트에 참여하거나(Contribute) Git 저장소를 복사하고 싶을 때 git clone 명령을 사용한다. 이미 Subversion 같은 VCS에 익숙한 사용자에게는 checkout이 아니라 clone이라는 점이 도드라져 보일 것이다. Git이 Subversion과 다른 가장 큰 차이점은 서버에 있는 모든 데이터를 복사한다는 것이다. git clone을 실행하면 프로젝트 히스토리를 전부 받아온다. 실제로 서버의 디스크가 망가져도 클라이언트 저장소 중에서 아무거나 하나 가져다가 복구하면 된다(서버에만 적용했던 설정은 복구하지 못하지만 모든 데이터는 복구된다 - 4장에서 좀 더 자세히 다룬다).

git clone [url] 명령으로 저장소를 Clone한다. Ruby용 Git 라이브러리인 Grit을 Clone하려면 아래과 같이 실행한다:

$ git clone git://github.com/schacon/grit.git
이 명령은 "grit"이라는 디렉토리를 만들고 그 안에 .git 디렉토리를 만든다. 그리고 저장소의 데이터를 모두 가져와서 자동으로 가장 최신 버전을 Checkout해 놓는다. grit 디렉토리로 이동하면 Checkout으로 생성한 파일을 볼 수 있고 당장 하고자 하는 일을 시작할 수 있다. 아래과 같은 명령을 사용하여 저장소를 Clone하면 "grit"이 아니라 다른 디렉토리 이름으로 Clone할 수 있다:

$ git clone git://github.com/schacon/grit.git mygrit
디렉토리 이름이 mygrit이라는 것만 빼면 이 명령의 결과와 앞선 명령의 결과는 같다.

Git은 다양한 프로토콜을 지원한다. 이제까지는 git:// 프로토콜을 사용했지만 http(s)://를 사용할 수도 있고 user@server:/path.git처럼 SSH 프로토콜을 사용할 수도 있다. 자세한 내용은 4장에서 다룬다. 4장에서는 각 프로토콜의 장단점과 Git 저장소에 접근하는 방법을 설명한다.

<span style="color: tomato; font-size:18px">수정하고 저장소에 저장하기<span>

만질 수 있는 Git 저장소를 하나 만들었고 워킹 디렉토리에 Checkout도 했다. 이제는 파일을 수정하고 파일의 스냅샷을 커밋해 보자. 파일을 수정하다가 저장하고 싶으면 스냅샷을 커밋한다.

**워킹 디렉토리의 모든 파일은 크게 Tracked(관리대상임)와 Untracked(관리대상이 아님)로 나눈다.** Tracked 파일은 이미 스냅샷에 포함돼 있던 파일이다. Tracked 파일은 또 Unmodified(수정하지 않음)와 Modified(수정함) 그리고 Staged(커밋하면 저장소에 기록되는) 상태 중 하나이다. 그리고 나머지 파일은 모두 Untracked 파일이다. Untracked 파일은 워킹 디렉토리에 있는 모든 파일이 스냅샷에 포함돼 있는 것은 아니고 Staging Area에 있는 것도 아니다. 처음 저장소를 Clone하면 모든 파일은 Tracked이면서 Unmodified 상태가 된다. 파일을 Checkout하고 나서 아무것도 수정하지 않았기 때문에 그렇다.

마지막 커밋 이후 아직 아무것도 수정하지 않은 상태에서 어떤 파일이 수정되면 Git은 그 즉시 파일을 Modified 상태로 인식한다. 그리고 이 수정한 파일을 Stage하고 Staged 상태인 파일을 커밋한다. 이 라이프사이클을 그림 2-1처럼 계속 반복한다.

![img](https://git-scm.com/figures/18333fig0201-tn.png)

그림 2-1. 파일의 라이프사이클
파일의 상태 확인하기
파일의 상태를 확인하려면 보통 git status 명령을 사용한다. Clone한 후에 바로 이 명령을 실행하면 아래과 같은 메시지를 볼 수 있다:
```
$ git status
On branch master
nothing to commit, working directory clean
```
위의 내용은 파일을 하나도 수정하지 않았다는 것을 말해준다. Tracked나 Modified 상태인 파일이 없다는 의미다. Untracked 파일은 아직 없어서 목록에 나타나지 않는다. 그리고 현재 작업 중인 브랜치를 알려준다. 기본 브랜치가 master이기 때문에 현재 master로 나오는 것이다. 브랜치 관련 내용은 차차 알아가자. 다음 장에서 브랜치와 레퍼런스에 대해 자세히 다룬다.

프로젝트에 README 파일을 만들어보자. README 파일은 새로 만든 파일이기 때문에 git status를 실행하면 'Untracked files'에 들어 있다:
```
$ vim README
$ git status
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)

    README

nothing added to commit but untracked files present (use "git add" to track)
```
README 파일은 Untracked files 부분에 속해 있는데 이것은 README 파일이 Untracked 상태라는 것을 말한다. Git은 Untracked 파일을 아직 스냅샷(커밋)에 넣어지지 않은 파일이라고 본다. 파일이 Tracked 상태가 되기 전까지는 Git은 절대 그 파일을 커밋하지 않는다. 그래서 일하면서 생성하는 바이너리 파일 같은 것을 커밋하는 실수는 하지 않게 된다. README 파일을 추가해서 직접 Tracked 상태로 만들어 보자.

파일을 새로 추적하기
git add 명령으로 파일을 새로 추적할 수 있다. 아래 명령을 실행하면 Git은 README 파일을 추적한다:

$ git add README
git status 명령을 다시 실행하면 README 파일이 Tracked 상태이면서 Staged 상태라는 것을 확인할 수 있다:

$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        new file:   README
'Changes to be committed' 에 들어 있는 파일은 Staged 상태라는 것을 의미한다. 커밋하면 git add를 실행한 시점의 파일이 커밋되어 저장소 히스토리에 남는다. 앞에서 git init 명령을 실행했을 때, 그 다음 git add (files) 명령을 실행했던 걸 기억할 것이다. 이것은 작업 디렉토리에 있는 파일들을 추적하기 시작하게 하였다. git add 명령은 파일 또는 디렉토리의 경로명을 아규먼트로 받는다; 만일 디렉토리를 아규먼트로 줄 경우, 그 디렉토리 아래에 있는 모든 파일들을 재귀적으로 추가한다.

####Modified 상태의 파일을 Stage하기
이미 Tracked 상태인 파일을 수정하는 법을 알아보자. benchmarks.rb라는 파일을 수정하고 나서 git status 명령을 다시 실행하면 결과는 아래와 같다:
```
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        new file:   README

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   benchmarks.rb
        ```
이 benchmarks.rb 파일은 Changes not staged for commit에 있다. 이것은 수정한 파일이 Tracked 상태이지만 아직 Staged 상태는 아니라는 것이다. Staged 상태로 만들려면 git add 명령을 실행해야 한다. git add는 파일을 새로 추적할 때도 사용하고 수정한 파일을 Staged 상태로 만들 때도 사용한다. git add를 실행하여 benchmarks.rb 파일을 Staged 상태로 만들고 git status 명령으로 결과를 확인해보자:
```
$ git add benchmarks.rb
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        new file:   README
        modified:   benchmarks.rb
        ```
두 파일 모두 Staged 상태이므로 다음 커밋에 포함된다. 하지만, 아직 더 수정해야 한다는 것을 알게 되어 바로 커밋하지 못하는 상황이 되었다고 하자. 이 상황에서 benchmark.rb 파일을 열고 수정한다. 아마 당신은 커밋할 준비가 다 됐다고 생각할 테지만, Git은 그렇지 않다. git status 명령으로 파일의 상태를 다시 확인해보자:

$ vim benchmarks.rb
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        new file:   README
        modified:   benchmarks.rb

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)

        modified:   benchmarks.rb
헉! benchmarks.rb가 Staged 상태이면서 동시에 Unstaged 상태로 나온다. 어떻게 이런 일이 가능할까? git add 명령을 실행하면 Git은 파일을 바로 Staged 상태로 만든다. 지금 이 시점에서 커밋을 하면 git commit 명령을 실행하는 시점의 버전이 커밋되는 것이 아니라 마지막으로 git add 명령을 실행했을 때의 버전이 커밋된다. 그러니까 git add 명령을 실행한 후에 또 파일을 수정하면 git add 명령을 다시 실행해서 최신 버전을 Staged 상태로 만들어야 한다:
```
$ git add benchmarks.rb
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        new file:   README
        modified:   benchmarks.rb
  

####파일 무시하기
어떤 파일은 Git이 자동으로 추가하거나 Untracked 파일이라고 보여줄 필요가 없다. 보통 로그 파일이나 빌드 시스템이 자동으로 생성한 파일이 그렇다. 그런 파일을 무시하려면 .gitignore 파일을 만들고 그 안에 무시할 파일 패턴을 적는다. 아래는 .gitignore 파일의 예이다:

$ cat .gitignore
*.[oa]
*~
첫번째 줄은 확장자가 .o 나 .a인 파일을 Git이 무시하라는 것이고 둘째 줄은 ~로 끝나는 모든 파일을 무시하라는 것이다. .o와 .a는 각각 빌드 시스템이 만들어내는 오브젝트와 아카이브 파일이고 ~로 끝나는 파일은 Emacs나 VI 같은 텍스트 편집기가 임시로 만들어내는 파일이다. 또 log, tmp, pid 같은 디렉토리나, 자동으로 생성하는 문서 같은 것들도 추가할 수 있다. .gitignore 파일은 보통 처음에 만들어 두는 것이 편리하다. 그래서 Git 저장소에 커밋하고 싶지 않은 파일을 실수로 커밋하는 일을 방지할 수 있다.

.gitignore 파일에 입력하는 패턴은 아래 규칙을 따른다:

아무것도 없는 줄이나, #로 시작하는 줄은 무시한다.
표준 Glob 패턴을 사용한다.
디렉토리는 슬래시(/)를 끝에 사용하는 것으로 표현한다.
느낌표(!)로 시작하는 패턴의 파일은 무시하지 않는다.
Glob 패턴은 정규표현식을 단순하게 만든 것으로 생각하면 되고 보통 쉘에서 많이 사용한다. 애스터리스크(*)는 문자가 하나도 없거나 하나 이상을 의미하고, [abc]는 중괄호 안에 있는 문자 중 하나를 의미한다(그러니까 이 경우에는 a, b, c). 물음표(?)는 문자 하나를 말하고, [0-9]처럼 중괄호 안의 캐릭터 사이에 하이픈(-)을 사용하면 그 캐릭터 사이에 있는 문자 하나를 말한다.

다음은 .gitignore 파일의 예이다:
```

```
# a comment - 이 줄은 무시한다.
# 확장자가 .a인 파일 무시
*.a
# 윗 줄에서 확장자가 .a인 파일은 무시하게 했지만 lib.a는 무시하지 않는다.
!lib.a
# 루트 디렉토리에 있는 TODO파일은 무시하고 subdir/TODO처럼 하위디렉토리에 있는 파일은 무시하지 않는다.
/TODO
# build/ 디렉토리에 있는 모든 파일은 무시한다.
build/
# `doc/notes.txt`같은 파일은 무시하고 doc/server/arch.txt같은 파일은 무시하지 않는다.
doc/*.txt
# `doc` 디렉토리 아래의 모든 .txt 파일을 무시한다.
doc/**/*.txt
```

**/ 스타일의 문법은 Git 1.8.2 버전부터 사용할 수 있다.

Staged와 Unstaged 상태의 변경 내용을 보기
단순히 파일이 변경됐다는 사실이 아니라 어떤 내용이 변경됐는지 살펴보기엔 git status 명령이 아니라 git diff 명령을 사용해야 한다. 보통우리는 '수정했지만, 아직 Staged 파일이 아닌것?'과 '어떤 파일이 Staged 상태인지?'가 궁금하기 때문에 git status 명령으로도 충분하다. git diff는 Patch처럼 어떤 라인을 추가했고 삭제했는지가 궁금할 때에 사용한다. git diff는 나중에 더 자세히 다룬다.

README 파일을 수정해서 Staged 상태로 만들고 benchmarks.rb 파일은 그냥 수정만 해둔다. 이 상태에서 git status 명령을 실행하면 아래와 같은 메시지를 볼 수 있다:

$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        new file:   README

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   benchmarks.rb
git diff 명령을 실행하면 수정했지만 아직 staged 상태가 아닌 파일을 비교해 볼 수 있다:

$ git diff
diff --git a/benchmarks.rb b/benchmarks.rb
index 3cb747f..da65585 100644
--- a/benchmarks.rb
+++ b/benchmarks.rb
@@ -36,6 +36,10 @@ def main
           @commit.parents[0].parents[0].parents[0]
         end

+        run_code(x, 'commits 1') do
+          git.commits.size
+        end
+
         run_code(x, 'commits 2') do
           log = git.commits('master', 15)
           log.size
이 명령은 워킹 디렉토리에 있는 것과 Staging Area에 있는 것을 비교한다. 그래서 수정하고 아직 Stage하지 않은 것을 보여준다.

만약 커밋하려고 Staging Area에 넣은 파일의 변경 부분을 보고 싶으면 git diff --cached 옵션을 사용한다(Git 버전 1.6.1부터는 좀 더 기억하기 쉽게 git diff --staged로도 사용할 수 있다). 이 명령은 저장소에 커밋한 것과 Staging Area에 있는 것을 비교한다:

$ git diff --cached
diff --git a/README b/README
new file mode 100644
index 0000000..03902a1
--- /dev/null
+++ b/README2
@@ -0,0 +1,5 @@
+grit
+ by Tom Preston-Werner, Chris Wanstrath
+ http://github.com/mojombo/grit
+
+Grit is a Ruby library for extracting information from a Git repository
꼭 잊지 말아야 할 것이 있는데 git diff 명령은 마지막으로 커밋한 후에 수정한 것들 전부를 보여주지 않는다. git diff는 Unstaged 상태인 것들만 보여준다. 이 부분이 조금 헷갈릴 수 있다. 수정한 파일을 모두 Staging Area에 넣었다면 git diff 명령은 아무것도 출력하지 않는다.

benchmarks.rb 파일을 Stage한 후에 다시 수정해도 git diff 명령을 사용할 수 있다. 이때는 Staged 상태인 것과 Unstaged 상태인 것을 비교한다:
```
$ git add benchmarks.rb
$ echo '# test line' >> benchmarks.rb
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        modified:   benchmarks.rb

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   benchmarks.rb
        ```
git diff 명령으로 Unstaged 상태인 변경 부분을 확인해 볼 수 있다:

$ git diff
diff --git a/benchmarks.rb b/benchmarks.rb
index e445e28..86b2f7c 100644
--- a/benchmarks.rb
+++ b/benchmarks.rb
@@ -127,3 +127,4 @@ end
 main()

 ##pp Grit::GitRuby.cache_client.stats
+# test line
Staged 상태인 파일은 git diff --cached 옵션으로 확인한다:

$ git diff --cached
diff --git a/benchmarks.rb b/benchmarks.rb
index 3cb747f..e445e28 100644
--- a/benchmarks.rb
+++ b/benchmarks.rb
@@ -36,6 +36,10 @@ def main
          @commit.parents[0].parents[0].parents[0]
        end

+        run_code(x, 'commits 1') do
+          git.commits.size
+        end
+
        run_code(x, 'commits 2') do
          log = git.commits('master', 15)
          log.size
변경사항 커밋하기
수정한 것을 커밋하기 위해 Staging Area에 파일을 정리했다. Unstaged 상태의 파일은 커밋되지 않는다는 것을 기억해야 한다. Git은 생성하거나 수정하고 나서 git add 명령으로 추가하지 않은 파일은 커밋하지 않는다. 그 파일은 여전히 Modified 상태로 남아 있다. 커밋하기 전에 git status 명령으로 모든 것이 Staged 상태인지 확인할 수 있다. 그리고 git commit을 실행하여 커밋한다:

$ git commit
Git 설정에 지정된 편집기가 실행되고, 아래와 같은 텍스트가 자동으로 포함된다(아래 예제는 Vim 편집기의 화면이다). 이 편집기는 쉘의 $EDITOR 환경 변수에 등록된 편집기이고 보통은 Vim이나 Emacs을 사용한다. 또 1장에서 설명했듯이 git config --global core.editor 명령으로 어떤 편집기를 사용할지 설정할 수 있다:

편집기는 아래와 같은 내용을 표시한다(아래 예제는 Vim 편집기):

```
```
# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
# On branch master
# Changes to be committed:
#       new file:   README
#       modified:   benchmarks.rb
#
~
~
~
".git/COMMIT_EDITMSG" 10L, 283C
```
```
자동으로 생성되는 커밋 메시지의 첫 줄은 비어 있고 둘째 줄부터 git status 명령의 결과가 채워진다. 커밋한 내용을 쉽게 기억할 수 있도록 이 메시지를 포함할 수도 있고 메시지를 전부 지우고 새로 작성할 수 있다(수정한 내용을 좀 더 구체적으로 남겨 둘 수 있다. git commit에 -v 옵션을 추가하면 편집기에 diff 메시지도 추가된다).

메시지를 인라인으로 첨부할 수도 있다. commit 명령을 실행할 때 아래와 같이 -m 옵션을 사용한다:
```
$ git commit -m "Story 182: Fix benchmarks for speed"
[master 463dc4f] Story 182: Fix benchmarks for speed
 2 files changed, 3 insertions(+)
 create mode 100644 README
 ```
commit 명령은 몇 가지 정보를 출력하는데 위 예제는 master 브랜치에 커밋했고 체크섬은 463dc4f이라고 알려준다. 그리고 수정한 파일이 몇 개이고 삭제됐거나 추가된 줄이 몇 줄인지 알려준다.

Git은 Staging Area에 속한 스냅샷을 커밋한다는 것을 기억해야 한다. 수정은 했지만, 아직 Staging Area에 넣지 않은 것은 다음에 커밋할 수 있다. 커밋할 때마다 프로젝트의 스냅샷을 기록하기 때문에 나중에 스냅샷끼리 비교하거나 예전 스냅샷으로 되돌릴 수 있다.

Staging Area 생략하기
Staging Area는 커밋할 파일을 정리한다는 점에서 매우 유용하지만 복잡하기만 하고 필요하지 않은 때도 있다. 아주 쉽게 Staging Area를 생략할 수 있다. git commit 명령을 실행할 때 -a 옵션을 추가하면 Git은 Tracked 상태의 파일을 자동으로 Staging Area에 넣는다. 그래서 git add 명령을 실행하는 수고를 덜 수 있다:
```
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   benchmarks.rb
```

no changes added to commit (use "git add" and/or "git commit -a")
$ git commit -a -m 'added new benchmarks'
[master 83e38c7] added new benchmarks
 1 files changed, 5 insertions(+)
이 예제에서는 커밋하기 전에 git add 명령으로 benchmarks.rb 파일을 추가하지 않았다는 점을 눈여겨보자.

####파일을 삭제하기
Git에서 파일을 제거하려면 git rm 명령으로 Tracked 상태의 파일을 삭제한 후에(정확하게는 Staging Area에서 삭제하는 것) 커밋해야 한다. 이 명령은 워킹 디렉토리에 있는 파일도 삭제하기 때문에 실제로 지워진다.

만약 Git없이 그냥 파일을 삭제하고 git status 명령으로 상태를 확인하면 Changes not staged for commit(즉, Unstaged) 에 속한다는 것을 확인할 수 있다:
```
$ rm grit.gemspec
$ git status
On branch master
Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        deleted:    grit.gemspec
```
no changes added to commit (use "git add" and/or "git commit -a")
그리고 git rm 명령을 실행하면 삭제한 파일은 staged 상태가 된다:

```
$ git rm grit.gemspec
rm 'grit.gemspec'
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        deleted:    grit.gemspec
```
커밋하면 파일은 삭제되고 Git은 이 파일을 더는 추적하지 않는다. 이미 파일을 수정했거나 Index에(역주, Staging Area을 Git Index라고도 부른다) 추가했다면 -f옵션을 주어 강제로 삭제해야 한다. 이 점은 실수로 데이터를 삭제하지 못하도록 하는 안전장치다. 한 번도 커밋한적 없는 데이터는 Git으로 복구할 수 없다.

또 Staging Area에서만 제거하고 워킹 디렉토리에 있는 파일은 지우지 않고 남겨둘 수 있다. 다시 말해서 하드디스크에 있는 파일은 그대로 두고 Git만 추적하지 않게 한다. 이것은 .gitignore 파일에 추가하는 것을 빼먹었거나 대용량 로그 파일이나 컴파일된 파일인 .a 파일 같은 것을 실수로 추가했을 때 쓴다. --cached 옵션을 사용하여 명령을 실행한다:

$ git rm --cached readme.txt
여러 개의 파일이나 디렉토리를 한꺼번에 삭제할 수도 있다. 아래와 같이 git rm 명령에 file-glob 패턴을 사용한다:

$ git rm log/\*.log
*앞에 \을 사용한 것을 기억하자. 파일명 확장 기능은 쉘에만 있는 것이 아니라 Git 자체에도 있기 때문에 필요하다. Windows 기본 쉘을 쓸 때는 \ 기호를 붙이지 않는다. 이 명령은 log/ 디렉토리에 있는 .log 파일을 모두 삭제한다. 아래의 예제처럼 할 수도 있다:

$ git rm \*~
이 명령은 ~로 끝나는 파일을 모두 삭제한다.

####파일 이름 변경하기
Git은 다른 VCS 시스템과는 달리 파일 이름의 변경이나 파일의 이동을 명시적으로 관리하지 않는다. 다시 말해서 파일 이름이 변경됐다는 별도의 정보를 저장하지 않는다. Git은 똑똑해서 굳이 파일 이름이 변경되었다는 것을 추적하지 않아도 아는 방법이 있다. 파일의 이름이 변경된 것을 Git이 어떻게 알아내는지 살펴보자.

이렇게 말하고 Git에 mv 명령이 있는 게 좀 이상하겠지만, 아래와 같이 파일이름을 변경할 수 있다:
```
$ git mv file_from file_to
```
잘 동작한다. 이 명령을 실행하고 Git의 상태를 확인해보면 Git은 이름이 바뀐 사실을 알고 있다:
```
$ git mv README.txt README
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        renamed:    README.txt -> README
        ```
사실 git mv 명령은 아래 명령어들을 수행한 것과 완전히 똑같다:
```
$ mv README.txt README
$ git rm README.txt
$ git add README
```
**git mv는 일종의 단축 명령어**이다. 이 명령으로 파일이름을 바꿔도 되고 mv 명령으로 파일이름을 직접 바꿔도 된다. 단지 Git의 mv명령은 편리하게 명령을 세 번 실행해주는 것뿐이다. 어떤 도구로 이름을 바꿔도 상관없다. 중요한 것은 이름을 변경하고 나서 꼭 rm/add 명령을 실행해야 한다는 것뿐이다.

---
### 4. git명령어 핵심정리 
다음을 보고 스스로 설명해보자 

- git init 
- git clone ~
- git add .gitignore
- git rm 
- git mv 
- git status 
- git commit 
- git commit -m 
- git add -a 
- git commit -A
- git branch "A" "B"
- git log 
- git branch 
- git branch --version
- git chekcout 
- git commit -v
- git commit --amend
- git reset HEAD benchmarks.rb
- git push 
- git remote
- git remote add pb https://github.com/paulboone/ticgit
- git pull 
- git tag
- git tag -a 
- git show