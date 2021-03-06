#3일차 숙제 by 최영민
####Index
<span style="font-size:18px;"> 1. ActiveX가 무엇일까?</span>

<span style="font-size:18px;">2. 국내 웹에 ActiveX가 정착되게 된 이유 및 배경</span>

<span style="font-size:18px;">3. 기술적 부채(Technical Debt)에 대해 알아보기</span>

<span style="font-size:18px;">4. 느낀점</span>
####참고자료 
[나무위키](https://namu.wiki/w/ActiveX)
[위키피디아](https://en.wikipedia.org/wiki/ActiveX)
[허핑턴포스트](http://www.huffingtonpost.kr/2015/03/24/story_n_6929144.html)
[how-to-geek](http://www.howtogeek.com/162282/what-activex-controls-are-and-why-theyre-dangerous/)
[윈도우스블로그](https://blogs.windows.com/msedgedev/2015/05/06/a-break-from-the-past-part-2-saying-goodbye-to-activex-vbscript-attachevent/)
 ---
 
####1. ActiveX가 무엇일까?

Active X는 마이크로소프트 사에서 개발한 일종의 browser add-on으로서, COM(Component Object Model)과 OLE(Object Linking and Embedding)을 활용한 기술이다. 기본적으로 Active X는 x86 환경에서 컴파일된 코드를 가지고 있기 때문에, 윈도우의 IE에서만 실행된다. 

마이크로소프사에서 소개하는 Active X는 다음과 같이 설명된다. 
>ActiveX is a binary extension model introduced in 1996 which allowed developers to embed native Windows technologies (COM/OLE) in web pages.

더 많은 설명을 하기 이전에 기본적인 용어들을 정리하자. 

- Binary Extension Model: 자바스크립트 혹은 HTML based와 대비되는 확장 모델. 

- OLE: 문서 혹은 다른 객체를 embedding하거나 linking 할 수 있는 윈도우의 기술. 

- COM(Component Object Model): 

- Interface: 컴퓨터 체계 내의 두 component 간에 정보의 교환이 일어나는 공유된 경계선. 여기서 component는 소프트웨어부터 하드웨어, 인간 등을 총칭하는 폭 넓은 의미이다. 

- ABI(Application Binary Interface): 2개의 프로그램 모듈 간의 인터페이스. 이중 1개는 라이브러리나 OS등 기계어 수준에 있다. 

- NPAPI: Netscape에서 만든 Active X와 비슷한 add-on으로서 윈도우와 IE에 종속되지 않으나 더 구시대의 기술이다. 

**Active X 의 강점**
1. 매우 손쉽고 빠르게 브라우저 환경에서 다양한 응용 프로그램을 실행시키거나 파일 생성, 삭제가 가능하다. 

**Active X의 단점**
1. 보안에 매우 취약하다. 이는 외국에서도 항상 언급되는 문제이다. Active X의 배포자가 아마존과 같이 신뢰할 수 있는 사이트여도, Active X를 대량 설치하게 되면 보안 문제가 생기기 매우 쉽다. 제3자가 Active X를 활용하여 사용자의 컴퓨터에 접근하는 것이 가능하기 때문이다. 
2. 호환성이 매우 떨어진다. 리눅스, 맥, 크롬, 파이어폭스는 윈도우 기술을 이용한 Active X를 실행할 수 없다. 


#### 2. 국내 웹에 ActiveX가 정착되게 된 이유 및 배경

첫 째, 인터넷 시대 초기에 Active X의 속도와 간편함은 자바 애플릿의 능력을 훨씬 상회하였다. 자바 애플릿의 성능은 인터넷 초기에 매우 느려 사용자들로부터 외면받았다. 

둘 째, 외국에 비해 마이크로소프트의 국내 점유율이 월등히 높다. 이로 인해 호환성의 문제가 두드러지지 않아 오랜 기간동안 Active X가 사라지지 않고 있다. 

셋 째, 정부의 정책 실패가 있었다. 일부 법조항에서는 해킹 문제등의 책임을 금융기관이 떠안도록 되어 있었기에 금융기관에서는 적극적으로 Active X등을 활용하여 그 책임을 다시 사용자에게 전가하였다. 이는 아마존과 같이 내부 서버에서의 보안 체계를 통해 보안 문제를 해결하는 관습과 대비 된다. 

넷 째, 보안에 대한 의식이 부족하다. 



#### 4. 느낀점

소프트웨어 역량과 보안의식이 너무나도 부족한 대한민국의 현주소를 알 수 있다. 국내Active X 문제도 결국에는 변화하는 인터넷 환경에 대해 인식할 수 있는 저변이 매우 약하다는 것을 반증한다. 조금 더 부연설명하자면 국내의 하드웨어 개발 수준에 비해 소프트웨어 역량은 매우 떨어진다고 할 수 있다. 세계 소프트웨어 100대 기업에 이름을 올린 국내 기업은 한군데도 없으며 국내소프트웨어는 안드로이드에 의존해왔다. 이는 삼성과 애플의 진부한 비교에서도 알 수 있다. 매번 새로운 스마트폰을 출시할 때 마다 삼성은 하드웨어의 진보를 내세우고, 애플은 소프트웨어와 감성적인 부분을 두드린다. __문제는 왜 이런 현상이 벌어지냐는 것이다.__

나의 진단은 __대한민국은 아직도 2차 산업혁명의 사고방식에 머물러 있기 때문__ 이라고 본다. 2차 산업혁명 시대의 유산인 조선, 철강, 자동차 산업 분야의 사고방식이 그대로 정보산업 분야에 존속하고 있다. 눈에 보이는 하드웨어를 더 빠르고, 작게 만드는 것에 우리는 능하다. 그러나 그것을 넘어서서 어떻게 소비자의 감성을 건드릴 것이며 새로운 기술과 하드웨어로 무엇을 할 것인가라는 질문에 들어서면 말문이 막히게 된다. 

보안은 이러한 문제의 연장성이라고 할 수 있다. 대한민국의 보안 실정은 1970년대 경부 고속도로 설치 전체적인 큰틀을 계획하고 인프라를 구축하는데에 약한 면이 그대로 보안에도 드러나는 것이다. 훌륭한 보안시스템과 솔루션이 개발되어도 이용자가 올바른 의식이 없다면 무용지물인 것이다. 
근본적인 문제에 도달하려는 사고방식의 부족 해결이 절실하다. 