# RAM

### RAM은 'Random Access Memory'의 약자다. 

RAM이라고 불리는 이유는 Random Access라는 말이 어떤 memory address든 곧바로 접근할 수 있다는 것 때문이다. 다른 보조기억장치들과 비교하여 지어진 , 자기디스크는 데이터에 접근하기 위해 순차적으로 할당 주소를 찾아가야 한다. 또한, 하드디스크를 예로들면 하드디스크는 데이터를 자기 물질로 기록하고 데이터를 읽기 위해 기록된 위치로 헤드를 움직이게 되는데, 이 헤드를 움직이는데에 시간이 많이 소요된다.


# 하버드 구조와 폰 노이만 구조의 한계

##### 하버드 구조:  

* 쓰이지 않는 free memory들이 쓰여지지 않는다. (free instruction memory를 data memory가 쓸 수 없고 또 그 반대로도)
* 두개의 bus로 구성하는것에 시간과 비용이 많이 든다.

##### 폰 노이만 구조:

* 직렬 처리 명령은 프로그램의 병렬 실행을 지원하지 않는다.
* 한개의 bus는 좁은 통로(bottleneck)여서 한 단위의 정보만이 접근될수 있다.
* 프로그램의 오류에 의해 명령어가 데이터와 같은 memory에 쓰여질 수 있다.

### 현재의 구성

현재까지 대부분의 컴퓨터는 폰 노이만 구조를 따라왔다. 최신의 컴퓨터 구조는 하버드 + 폰 노이만의 결합형이다. CPU(중앙처리장치) 외부적으로는 폰 노이만 구조를 쓰고 내부적으로는 하버드 구조를 적용해서 속도를 향상시켰다. 하지만 메모리 속의 프로그램을 순차적으로 실행하는 폰 노이만의 구조 자체는 변하지 않았다.


# 한글을 표현할 수 있는 인코딩 방식

* UTF-8
* EUC-KR
* CP949

#### UTF-8:
유니코드 인코딩 방식중 하나이며 조합형 방식의 Character Set이다. ASK|| 문자들을 표현할 수 있기에 유니코드 인코딩에서 가장 대표적인 방식이다.  

장점: 서버 운영체제와 웹서버를 UTF-8로 제작시 별도로 인코딩이 필요없다. 다른 국가에서 한글 언어팩이 설치되지 않아도 한글 표현 가능하다. 다양한 언어로 작성되는 환경에 더 유리하다.

단점: 한글이 보통 3 byte가 할당되서 한글 표현시 EUC-KR보다 용량을 더 차지한다.

#### EUC-KR, CP949:

EUC-KR과 CP949는 완성형 인코딩 방식이고 한글을 2 byte로 할당한다.
CP949는 EUC-KR방식을 마이크로소프트에서 확장시킨 방식.

장점: EUC-KR, CP949는 UTF-8에 비해 한글 표현시 용량을 적게 차지한다.

단점: 완성형이기에 표현할 수 있는 부분에 한계가 있다. 특히 웹에서 글로벌 트렌드는 UTF-8인데, 한국에 윈도우 의존도가 높아 EUC-KR이나 CP949로 인코딩한 것이 많아서 생기는 충돌이 나타난다.
