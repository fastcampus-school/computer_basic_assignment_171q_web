
## RAM
Random Access Memory(컴퓨터의 주 기억장치)

* ROM(Read Only Memory, 보조기억장치)과 달리 '자유롭게 읽고 쓸 수 있다 '. 전원이 끊기면 지워지는 휘발성 기억 장치이다.

* RAM이란 '임의 접근 메모리'이다. 즉 메모리의 어느 주소로든 바로 접근 할 수 있다는 의미이며 순차 접근 메모리(Sequential Access Memory)의 반대개념이다. 예를 들어 카세트테이프가 SAM 이라고 할 수 있다. 따라서 보조기억장치인 하드디스크도 일종의 RAM 인 것이다. 그러므로 RAM은 다음과 같이 분류되어지는 게 정확하다.
	1. Read Only Memory(ROM)
	2. Read Write Memory(RWM)
	
* 그럼에도 RAM이 개발 되었을 당시에는 이미 RWM을 SAM의 세분화된 메모리 방식을 일컫는 용어로 선정했었기 때문에 현재와 같이 주기억장치로서 RAM이라고 부른 것이라고 한다.

그렇다면 왜 RAM과 ROM 두가지로 나누어지는 구조를 선택했을까?


## 하버드 구조와 폰-노이만 구조
* Von Neumann Architecture
	1. one storae system(memory) for "both" storing data and program to be executed.
	2. A single set of address/data buses between CPU and memory
	3. therefore, for each two cycles are needed to complete an instruction.

* Harvard Architecture
	1. Two separate memories for storing "data" and "program"
	2. Two sets of address/data buses between CPU and memory
	3. therefore, processor can complete an instruction in one cycle "if appropriate pipelining startegies are implemented".

* Currently, most computer architecture is the mixture of the two. There is no physical separation between data and program in modern CPU. Inside, however, modern computers do implent mechanisms of harvard architecture.



## 한글 표현 문자 인코딩
* 한글 표형 형태는 조합형과 완성형 방식 두 가지로 나뉠 수 있다. 초성, 중성, 종성을 따로 인식하고 각각을 하나의 바이트로 인식하고 조합하는 조합형이 가장 한국과 맞는 방식이며 넓은 확장성을 가지고 있다. 그런데...
* 한국에서는 Windows가 가장 높은 점유율을 차지하고 윈도우의 인코딩 방식은 기본적으로 완성형이다. 그럼에도 EUC-KR(2,350자)에서 진화한 CP-949(11,172자) 방식은 쓸 수 있는 모든 한글을 포함한다고 볼 수 있다. 그런데...
* Web server나 DB의 경우 UTF-8과 EUC-KR 중에서 인코딩을 맞춰야 문자표현이 가능하다...
