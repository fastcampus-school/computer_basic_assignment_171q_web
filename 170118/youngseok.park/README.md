###1. RAM 정리

* RAM : Random Access Memory
*  CPU와, RAM, I/O(입출력) 장치를 연결하는 통로인 시스템버스를 가지고 있으며 이 시스템 버스는 총 3가지 형태가 있다.

>	1. 데이터버스 : 주기억장치(RAM)으로부터 읽거나 쓸 데이터가 전송되며  데이터버스 크기는 CPU가 한 번에 전송 가능한 데이터 크기와 같으며 양방향 버스이다
>	2. 주소버스 : 주소버스를 통해 주기억장치의 데이터를 읽고 쓰기 위한 주소 또는 입출력장치가 결정되며 단방향의 버스이다.
>	3. 제어버스 : 제어버스는 외부장치에서 cpu에 어떤 동작을 요구하는 각종  제어 신호가 전송 된다

* CPU와 RAM은 데이터버스와 주소버스를 통해 전송을 주고 받는데, 데이터 전송량은 CPU가 한 번에 전송 가능한 데이터 크기와 같으며, CPU가 데이터 주소를 단방향으로 메모리에 전송 후에 사용시에는 해당 주소로 데이터에 임의로 접근하여 사용하기 때문에 RAM이라고 한다. 


###2. 하버드 구조와 폰 노이만 구조

RAM은 컴퓨터 실행시 컴퓨터 작동에 필요한 프로그램 파일을 상주시키면서 데이터를 CPU와 주고 받는다. 메모리에 상주하는 종류는 크게 2가지로 나눈다

* 프로그램 메모리 : 실행되는 프로그램 그 자체를 저장하는 읽기 전용 메모리
* 데이터 메모리 : 읽기와 쓰기가 가능한 데이터 저장 전용 메모리

1) 폰 노이만 구조 문제점

* 폰 노이만 구조는 프로그램 메모리와 데이터 메모리가 하나의 메모리로 구현되어 하나의 Bus로 데이터를 액서스 하게 되는데, 데이터를 읽고 쓰는것을 동시에 하지 못하기 순차적으로 해야 하는 때문에 병목현상이 나타나게 된다.

2) 하버드 구조 문제점

* 하버드 구조는 폰 노이만의 구조의 문제점이었던 하나의 메모리에 구성된 프로그램 메모리와 데이터 메모리를 분리시켜 병목현상을 해소 하였으나, 프로그램 메모리에 데이터가 섞여 있는 경우, 데이터 메모리에서 찾는 특수한 경우 문제가 생길 수 있다. 

3) 폰 노이만 구조의 보완

* 폰 노이만의 병목 현상은 크게 3가지 형태로 보완이 이루어지고 있다

>	1. RAM의 성능을 CPU급으로 올려서 성능 차를 최소화 하는 방향
>	2. CPU-RAM-보조 기억 장치의 3단계를 2단계로 줄이는 방향
>	3. CPU 내부에 일반 램보다 더 빠른 캐쉬 메모리를 탑재하는 방향

###3. 한글 표현하는 문자 인코딩 방식

* 한글 인코딩은 크게 두가지로 나뉘게 되는데, 자음과 모음의 조합으로 글자를 표현하는 조합형과 한글의 하나의 독립된 글자로 인식한 완성형이 있다. 

1. 조합형 : 바이트 단위로 데이터 용량이 중요하던 시절 영어가 1바이트로 구성될 때 한글은 자음과 모음등의 조합 때문에 2바이 이상을 차지하여 용량 문제가 그 당시에는 있었다.

2. 완성형 : 한글자에 코드를 부여하여 용량은 줄일 수 있었지만 완성형으로 인정된 한글 이외에는 표현 할 수 없었던 문제가 있었다.

