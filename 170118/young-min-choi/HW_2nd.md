# 2일차 숙제

####Index
<span style="font-size:18px;"> 1. RAM은 어떤 단어들의 약자이며, 왜 RAM이라고 부르게 되었을까?</span>

<span style="font-size:18px;">2. 하버드 구조와 폰 노이만 구조의 한계는 각각 무엇이며 지금은 어떻게 구성된 모습으로 사용되고 있을까?</span>

<span style="font-size:18px;">3. 한글을 표현할 수 있는 문자 인코딩 방식에는 무엇이 있을까? 각각의 장단점도 조사해 보세요.</span>
 ---
 
####1. RAM은 어떤 단어들의 약자이며, 왜 RAM이라고 부르게 되었을까?

- RAM은 Random Access Memory의 준말이다.  


- Random-access의 뜻은 무엇일까?

이를 위해 random의 사전적 정의를 찾아보자. 

```
Statistics. of or characterizing a process of selection in which each item of a set has an equal probability of being chosen.
```
주목해야 할 부분은 이 부분이다. 
```
 equal probability of being chosen
```
__결국 random-access란 각 메모리가 선택될(chosen) 속도가 물리적 위치와 무관하다는 것을 뜻한다.__

- 그러면 물리적 위치에 영향을 받는 메모리에는 어떤 것들이 있을까?
Hard disk, CDRW, Drum memory 

- RAM은 어떻게 구성되어 있길래 random-access가 가능할까? 
RAM은 기본적으로 전류를 이용하여 data를 저장한다.
그러므로 전류가 꺼지면? data가 모두 지워진다. 

**RAM은 주 메모리 이면서 동시에 임시(temporary)메모리라고 불린다는 점을 명심하자.** 

- RAM의 진화과정  RIMM, DIMM, DRAM, SDRAM, DDR.. 

[참고 유투브 링크](https://www.youtube.com/watch?v=PVad0c2cljo)


D-RAM: Dynamic RAM의 준말로서 Dynamic 하다는 것은 내부에 capacitors를 저장하고 있는데 이  capacitor를 전류로 계속 refresh 시켜줘야 함을 의미한다. 

SDRAM: Synchorized DRAM, 기존의 DRAM과 비교하여 system clock과 동기화가 되어 더 효율적으로 data를 보내는 것이 가능해졌다. 

DDR - 컴퓨터의 clock signal을 up and down 을 모두 활용하여 보내는 것이 가능해졌다. 이로 인해 보낼 수 있는 데이터의 양이 두배로 늘어났다.

DIMM - Dual Inline Memory Module의 준말로 Inline이  RIMM에 비해 두배 많으므로 두배의 bus를 확보할 수 있다. 

**결론적으로, RAM의 속도는 clock signal과 bus의 bandwidth를 늘리는 것 등 데이터를 더 많이 효율적으로 보내는 것에 의해 가능해졌다고 볼 수 있다. **

---

####2. 하버드 구조와 폰 노이만 구조의 한계는 각각 무엇이며 지금은 어떻게 구성된 모습으로 사용되고 있을까?

다음 영문 자료를 참조 했습니다. [참조](http://infocenter.arm.com/help/index.jsp?topic=/com.arm.doc.faqs/ka3839.html)

먼저 본격적으로 들어가기 전에 알아야될 기본적인 용어들을 학습하자. 

1. literal: a notation for representing a fixed value in source code. 

2. literal pool: a lookup table used to hold literals during assembly and execution.

3. cache memory: Cache memory, also called CPU memory, is random access memory (RAM) that a computer microprocessor can access more quickly than it can access regular RAM. This memory is typically integrated directly with the CPU chip or placed on a separate chip that has a separate bus interconnect with the CPU. The basic purpose of cache memory is to store program instructions that are frequently re-referenced by software during operation. Fast access to these instructions increases the overall speed of the software program.
**한마디로 캐쉬란 RAM의 일종인데 CPU에 자체적으로 붙어 자주 반복되는 명령 메모리들을 저장해두기 위함이다.

4. self modifying code: 자체 수정 코드는 실행 중에 자신의 명령어를 바꾸는 코드를 말한다. 주로 명령어 경로 길이 (instruction path length)를 줄이고, 성능을 향상시키거나 비슷한 반복되는 코드를 줄임으로써 유지보수를 단순화 시켜준다. 자체 수정 코드는 주로 테스트될 필요가 있는 조건의 수를 줄이는데 사용되는 조건부 프로그램 분기와 "플래그 설정" 방식의 대체재이다.

5. instruction: Program consists of a sequence of instructions. 
**프로그램이란 실행의 그룹이다. 실행은 프로그램을 이루는 기본단위이다.**

6. 임베디드 시스템(embeded system): 임베디드 시스템(영어: embedded system, 내장형 시스템)은 기계나 기타 제어가 필요한 시스템에 대해, 제어를 위한 특정 기능을 수행하는 컴퓨터 시스템으로 장치 내에 존재하는 전자 시스템이다. 즉, 임베디드 시스템은 전체 장치의 일부분으로 구성되며 __제어가 필요한 시스템을 위한 두뇌 역할을 하는 특정 목적의 컴퓨터 시스템__이다. 이에 비해 개인용 컴퓨터와 같은 특정되지 않는 일반적인 목적을 수행하는 컴퓨터 시스템과 대조된다.

**cache가 없는 상태의 기본적인 두 구조를 비교해보자.**

| 하버드 | 폰노이만|
|---|---|
|Bus가 두 개| bus가 한개|
|더 복잡한 cpu가 필요| 간단한 cpu가 필요|
|병목 현상이 일어나지 않음 | 병목 현상이 가능함|
|부피가 더 크고 비싸다|부피가 싸고 저렴하다| 
|메모리와 ALU가 분리| 메모리, 연산이 통합|
|rewrite가 불가능하다|rewrite가 가능하다|
|메모리와 연산이 다른 cell크기를 가지는 것 가능|불가능|

**둘의 구조차이는 기본적으로 메모리가 통합되어 있는지, 그에 따라 버스가 1개인지 2개인지로 구분된다. **

이는 그림을 통해 더 명확히 알 수 있다. 

![img](http://www.edgefxkits.com/blog/wp-content/uploads/Differences-between-Von-Neuman-Architecture-and-Harvard-Architecture.jpg)

cache는 이러한 기본적인 두 구조의 한계를 극복하는데 사용된다. 
하버드에서는 메모리와 연산을 위한 각기 다른 캐쉬를 가지는 것이 좋은데, 이를 통해 양쪽의 bus가 동시에 쓰이는 것을 가능하게 하며 이것이 하버드 구조가 기본적으로 지향하는 방향이기 때문이다. **즉 다시 말해, shared cache를 쓰는 것은 하버드 구조에서는 바람직 하지 않은데 그 이유는 두 bus를 동시에 feeding 하는 것이 힘들어 지기 때문이다.** 하버드 구조는 주로 high-performance system에서 자주 활용되고 이런 환경에서는 cache가 쓰이는 것이 매우 효율적이다. 

---
####3. 한글을 표현할 수 있는 문자 인코딩 방식에는 무엇이 있을까? 각각의 장단점도 조사해 보세요.

기본적으로 완성형과 조합형이 있다. 

|완성형|조합협|
|---|---|
|모든 문자에 관해 완성된 형태를 저장한다.|각 자음 모음을 저장하고 이를 조합|
|차지하는 데이터가 많다|차지하는 데이터가 적다|


- 한글 조합형

한글 조합형은 1980년대 초반부터 1990년대 중반까지 널리 사용된 문자집합이다. 현재는 거의 쓰이지 않는다.

- 한글 완성형 – KS X 1001 (KSC5601-1987)

한국 산업 규격의 한국어 문자 집합으로 정식명은 "정보 교환용 부호계 (한글 및 한자)" 이다. 

- 한글 완성형 인코딩 – EUC-KR

EUC-KR은 AT&T에서 아시아계 문자를 표현하기 위해 만든 확장 유닉스 코드(EUC, Extended Unix Code)이다. EUC-CN(중국어), EUC-TW(대만), EUC-JP(일본) 등이 존재한다.

- 한글 완성형 인코딩 – CP949

EUC-KR에서 표현하지 못하는 문자를 표현하기 위해 마이크로소프트에서 만들었다. 따라서 인터넷 정보 교환의 표준은 아니다.

- 유니코드 (Unicode)

유니코드는 전 세계 모든 문자를 일관되게 표현하기 위해 정해진 산업 표준이다.