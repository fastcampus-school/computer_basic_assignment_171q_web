## 버전 관리 시스템(version control sytem)
**파일의 변화를 시간에 따라 기록**했다가 나중에 특정 시점의 버전을 다시 꺼내올 수 있는 시스템이다.   
거의 모든 컴퓨터 파일의 버전을 관리의 대상이 된다.   
그래픽 디자이너나 웹 디자이너도 버전 관리 시스템을 사용할 수 있다.  

>변경 이력을 기록을 통해서 변경된 내용을 공유 가능하다.  
타인이 작업한 태용을 쉽게 병합한다.  
과거 상태로 쉽게 복구 가능하다.   
여러 분기(branch)를 이용해 병렬 관리가 가능하다.  

**즉, 관리가 용이하다.**  


### 여러가지 버전 관리 방법

#### 로컬 버전 관리 시스템
버전을 관리하기 위한 가장 쉬운방법으로 작업 중인 파일을 다른 디렉토리에 복사하는 것이다.  
엉뚱한 파일을 덮어쓰거나 의도하지 않은 위치로 복사하는 등의 실수가 발생할 수 있다는 단점이 있다. 위와 같은 문제를 해결하기 위해 데이터베이스에 파일의 변경 사항을 기록하는 로컬 버전 관리 시스템을 만들었다. `RCS`가 대표적인 로컬 버전 관리 시스템이다.

#### 중앙 집중식 버전 관리 시스템
여러 명의 개발자와 함께 작업할 때는 로컬 버전 관리시스템에 한계가 있어서 개발되었다.
중앙 집중형 버전관리 시스템은 모든 파일을 저장하는 중앙서버와, 이 중앙서버에서 파일들을 가져오는(체크아웃) 여러 클라이언트가 존재한다. 클라이언트의 마지막 스냅샷을 통해 중앙 서버의 버전을 관리한다. 

- 다른 작업자가 무엇을 하고 있는지 알 수 있다.
- 중앙 서버가 다운되면 진행중이던 버전 관리를 할 수 없다.
- 중앙 서버의 하드디스크에 오류가 발생하고, 백업도 해놓지 않았다면 개발자 각자의 로컬 컴퓨터에 가지고 있던 스냅샷을 제외한 모든 자료를 잃게 된다.

#### 분산 버전 관리 시스템
분산버전관리시스템에서는 클라이언트의 스냅샷을 가져오는 대신 저장소를 통째로 복제하는 방식을 사용한다. 서버에 문제가 생겨도 클라이언트에 존재하는 저장소를 서버로 복사하면 서버가 복구된다. `Git`, `Mecurial` 등이 분산 버전 관리 시스템에 속한다.

- 로컬과 원격모두 고유의 저장소를 가질 수 있다
- 저장소만 복사하면 어떤 컴퓨터에서든 버전을 관리할 수 있다.
- 다수의 원격 저장소를 가지는 것이 가능하기 때문에 여러 그룹과 함께 작업 할 수 있다.


## git 명령어를 알아보기
git의 명령어는 모두 "git"이란 단어로 시작된다

git --help를 쳤을 때 나오는 명령어들  
**start a working area**  

- `clone`
   + 깃저장소를 복제해서 local repository를 생성한다  
     (Clone a repository into a new directory)  
- `init`  
   + 깃 저장소를 초기화한다. 저장소나 디렉토리 안에서 이 명령을 실행하기 전까지는 그냥 일반 폴더고, 이것을 입력해야 추가적인 git 명령어등을 줄 수 있다.   
   (Create an empty Git repository or reinitialize an existing one)  

**work on the current change**  

- `add`
   + 작업 폴더의 파일을 git이 추적하게 하거나 commit을 위한 준비상태로 만듦  
     (Add file contents to the index)  
- `mv`
   + 파일 이동을 하거나, 이름 변경하기  
     (Move or rename a file, a directory, or a symlink)  
- `reset`
   + add로 등록한 파일은 unstaged상태로 바꿔준다  
     (Reset current HEAD to the specified state)  
- `rm`
   + 파일, 폴더를 삭제한다  
     (Remove files from the working tree and from the index)  

**examine the history and state**  

- `bisect`
   + 버그가 어디서 생겼는지 찾아준다  
     (Use binary search to find the commit that introduced a bug)  
- `grep`
   + 검색어가 들어가있는 파일을 찾을 수 있다  
     (Print lines matching a pattern)  
- `log` 
   + commit의 히스토리를 조회한다.  
     (Show commit logs)  
- `show`
   + 현재 HEAD의 커밋정보를 조회한다.  
     (Show various types of objects)  
- `status`  
   + 저장소(repository)의 상태를 확인한다.    
    (Show the working tree statu)  

**grow, mark and tweak your common history**  

- `branch`  
   + 브랜치의 리스트를 확인하거나, 새로운 브랜치를 만들거나, 그것을 지울 수 있다.  
     (List, create, or delete branches)  
- `checkout`    
   + 원하는 브랜치로 이동하게 해주는 명령어이다.  
    (Switch branches or restore working tree files)  
- `commit`  
   + Local Repository에 올리기 위해 사용한다.  
    작업한 내용에 대한 정보를 작 정리해서 적어놓는다  
    간단하게 입력하기 위해서 뒤에 `- m`을 입력할수도 있다.  
    (Record changes to the repository)  
- `diff` 
   + local과, remote작업 간의 변경 내역을 표시한다.  
     (Show changes between commits, commit and working tree, etc)   
- `merge`  
   + 현재 브랜치와 다른 브랜치를 병합할 수 있다.  
   합쳐질 branch log의 번호를 기억해두었다가, 본체가 될 branch에서 `git merge lognumber`를 적어서 병합시킨다.  
   (Join two or more development histories together)    
- `rebase` 
   + 브랜치의 변경사항을 순서대로 다른 브랜치에 적용하며 병합한다.  
     저장소의 커밋 로그와 이력을 한 줄로 정리해주므로, 
     완료된 브랜치를 마스터에 병합할 때 사용한다.  
    (Reapply commits on top of another base tip)   
- `tag`
   + 태그를 생성하고, 조회하고, 지울 수 있다   
     (Create, list, delete or verify a tag object signed  with GPG)  

**collaborate**  

- `fetch`
   + remote의 데이터를 모두 가져오지만 merge는 생략한다.  
     서버의 데이터를 확인하는 용도로 사용   
     (Download objects and refs from another repository)  
- `pull`  
   + 원격 repository에서 변경 사항을 다운로드한다. merge를 자동수행한다.   
     (Fetch from and integrate with another repository or a local branch)  
- `push`  
   + Local repository의 commit된 데이터를 원격 repository로 업로드시킨다.  
     (Update remote refs along with associated objects)  

**추가사항**

- `remote`
   +  remote서버 확인
