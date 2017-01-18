# 버전관리란 무엇인가?

> 버전(version)은 변경된 이력을 의미한다 ... 버전관리 시스템은 코드의 변화를 관리하는 시스템이다. 각각의 변화들을 저장해서 현재 코드의 상태가 어떤 맥락을 거쳐서 지금의 상태가 되었는지를 파악하고, 문제가 생겼을 때 과거로 돌리는 등의 기능을 제공한다. 특히 코드라는 중요한 데이터를 안전하게 보관한다는 의미에서 백업의 기능도 하게 된다. 또, 여러 사람이 협업을 할 때 발생할 수 있는 충돌이나 유실을 방지하는 역할도 훌륭하게 수행한다 - 생활코딩

강의를 통해 배운 내용과 생활코딩에서 quote해온 것을 통해 버전관리란 여러 사람이 어느 프로젝트(특정 분야에 한하지 않고)를 마치는 과정에서 데이터의 충돌이나 유실을 최소화 하고 효율적으로 원하는 값을 얻기 위해 요구되는, 또한 그 값을 더 발전시키기 위해 필요한 과정이라고 생각한다.

특히 학교에서 수강한 소프트웨어 공학시간에 Agile development의 접목과 client 요구사항에 대응하는 도구로서 현재 개발 환경에 아주 적합한 관리법이라 생각한다.

# git commands 

* **git init** : 현재 있는 working directory에 .git 폴더 생성.
* **git clone** : remote 저장소를 통째로 working directory에 복사, 또는 현재의 directory를 통해 local clone을 진행 할수있다.
```
git clone https://github.com/Jinsoo89/...
```

* **git status** : 현재 working directory의 상태를 확인

* **git log** : 현재 branch 내에서 일어난 commit들을 보여줌 (history)
```
  git log --all --graph   <--(branch들과 commit위치들을 선을 이용한 그림으로 보여줌)
```

* **git add** : 새로 생성되거나 변경된 파일을 working directory에서 stage단계로 올림.  
```
  git add index.html
```
```
  git add --all <---(status에 나온 변경된 파일들을 한번에 올려줄때)
```
* **git commit** : stage에 올라온 파일을 local repository에 올리고 comment를 작성.
```
  git commit index.html
```
```
  git commit --all -m "comment까지 한번에 달아줄때"
```

* **git push** : remote repository로 local repository에 올려진 파일, comment를 보내 적용함.
```
  git push  <--(현재의 branch의 remote로 보냄)
```
```
  git push origin master  <--(remote의 master branch로 보냄)
```

* **git pull** : remote repository에 있는 정보를 가져와 working directory에 적용해 병합시킴.

* **git fetch** : remote repository의 변경사항을 local repository에 적용.

* **git revert** : 특정 commit에서 변경된 내역을 취소하는 새로운 commit생성.
```
  git revert 943cd2093201dkascmdl2092032   <--(변경내역을 취소하려는 commit의 고유번호)
```

* **git branch** : branch 생성 혹은 관리 명령어.
```
  git branch  <--(생성된 branch 리스트 보여줌)
```
```
  git branch dev  <--(dev라는 branch 생성)
```
```
  git branch dev master <--(dev라는 branch를 master branch안에 생성)
```

* **git checkout** : branch 이동 관련 명령어.
```
  git checkout master  <--(master branch로 이동)
```
```
  git checkout -b html <--(html이라는 branch를 생성하고 html branch로 이동)
```

* **git merge** : branch 와 branch를 merge한다. (접목시킨다? 합체?)
```
  git merge 430cd3490382skld2090sadkl   <--(접목시키려는 branch내 특정 위치의 commit 고유번호)...(이 명령어 실행 위치는 merge당하는 branch)
```

