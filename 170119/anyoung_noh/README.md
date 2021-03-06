##ActiveX
<!--마이크로소프트사가 개발한 COM(component object model)과 OLE(Object linkin and embedding)을 적용해 만든 기술이다. www로부터 다운로드받은 컨텐츠를 이용하는데에 이용된다. ActiveX는 전반적인 기술 혹은 기술을 구현하는데 필요한 구성요소를 가리키며, ActiveX Control은 ActiveX를 이용해 만든 작은 프로그램을 말한다. 대부분 ActiveX는 IE의 플러그인을 만드는데 사용된다.-->

WWW서비스 이래로 다양한 형태(동영상과 음원 재생, 금융업무 등)가 등장하면서 단순 HTML 문서로만 모든 기능을 이용하기 어려워졌다. 따라서 웹 브라우저와 연동되는 프로그램을 사용자의 PC에 설치하여 웹브라우저의 기능을 확장시키는 방법이 생겨났다. 사용자의 PC에 추가적으로 설치하는 프로그램을 Plug-in이라고 하는데 ActiveX도 이러한 Plug-in의 한 종류이다.  

마이크로소프트의 Windows는 범용성에 초점을 맞춘 OS였고 따라서 PC 운영체제들 중 가장 높은 점유율을 갖게된다. Windows의 내장 웹브라우저가 IE이다 보니 ActiveX가 자연스럽게 대표적인 웹브라우저 Plug-in이 되었다. 

####ActiveX의 장점
`서비스 제공자의 편의성이 매우 높다`  
일단 ActiveX를 설치하게되면 사용자가 PC에서 이를 실행하는 것 만으로도 웹사이트와 기능이 연동되기 때문에 웹사이트에서 매우 간편하게 사용자의 PC를 제어할 수 있다. 

`웹브라우저 및 웹사이트의 기능을 거의 제한없이 확장할 수 있다`  
이러한 장점 때문에 멀티미디어 컨텐츠 구동용, 금융 거래용, 관공서용 등 많은 ActiveX가 개발되었다.

####ActiveX의 단점 - 호환성과 보안성 취약
__`IE에서만 쓸 수 있다.`__  
IE가 PC용 웹 브라우저 시장에서 가장 높은 점유율을 차지하고 있으나 2000년대부터 모질라의 FireFox, 구글의 Chrome과 같은 웹브라우저의 점유율이 크게 올랐으며 2011년에는 전세계 시장에서 IE의 점유율이 60%이하로 떨어졌다. 또한 Windows기반의 PC가 아닌 스마트폰과 태블릿컴퓨터에서는 ActiveX에서는 전혀 사용할 수 없다.

__`사용자의 PC에 직접 설치되는 특성 악용`__  
악성코드를 심거나 개인정보를 유출하는 사례가 발생하며 사용자가 원하지 않는 기능들까지 함께 설치되는 경우가 많다.

__`PC의 처리 속도 저하`__  
과도한 ActiveX의 설치는 PC의 전반적인 처리 속도를 크게 저하시킨다.


##국내 웹에 ActiveX가 정착되게 된 이유 및 배경

####책임
국내에서는 정부기관과 금융 및 쇼핑몰 사이트까지 ActiveX를 애용했다. 정부기관의 서비스가 ActiveX를 사용하니 여타 민간 서비스에서도 ActiveX가 성행했다. 하지만 각종 보안사고가 일어나자 책임에 대한 이슈가 대두되었다. ActiveX의 불편과 위험으로 인한 피해를 책임지고 보상해야하는 주체가 있어야 하지만 이를 기피하고 있는 것이다. 

####개발적 측면
과거 웹에서 많은 기능을 지원하지 않았을 때, 국내는 마이크로소프트사의 점유율이 높았고 때문에 ActiveX를 사용해 요청사항을 구현하는 일이 빈번했다. 처음부터 ActiveX를 이용해 구현을 하다보니 새로운 기술이 나와도 ActiveX를 지속적으로 사용하는 것이 더 쉬운 일이었던 것이다. 


##Technical Debt(기술 부채)
기술 부채(Technical debt)는 워드 커닝햄(Ward Cunningham)이 창안한 은유이다.  
통상적으로 사용되는 '부채'는 이자를 내고 돈을 쓰는 시점을 당기는 것이라면, '기술부채'는 기술적으로 해결해야할 일들을 미루고 비지니스적인 문제를 해결하는 시점을 당기는 것이다.  

일을 빠르게, 지저분한 방식으로 처리하면 후일 추가적인 개발로 이자를 내게되는 것이다. 기술 부채를 지게 되었을 때, 이자를 계속 내거나 과거의 설계 방식을 리팩토링으로 개선하여 원금을 갚을 수 있다. 리팩토링을 하면 당장은 비용이 들지만 앞으로의 이자가 줄어들게 되는 것이다.  

시장 기회를 얻으려고 노력하면 개발자는 마감을 지키기 위한 기술부채를 지게된다. 이는 특정 시점에는 실용적인 방법이 될 수 있으나 훗날 리팩토링을 거치지 않는다면 감당하지 못할 부채가 쌓이고 이자를 내기 위해 개발자 리소스를 허비하게 되는 위험이 존재한다. 


##ActiveX와 기술 부채
이번 이슈를 조사하면서 ActiveX로 인한 국내에서는 왜 이 문제를 해결하지 못하고 있는지에 대해 조금이나마 알 수 있었다. 문제적 환경의 개선을 위한 시스템 컨트롤이 너무나 부진하고 무능력하다고만 생각했었다. 책임 이슈나 개발 이슈에 대해서는 깊게 생각한 적이 없었다. 물론 금융서비스와 보안이슈에 대해서는 책임을 지는 것이 당장 큰 손해처럼 느껴질 것이다. 그러나 국가적 차원에서 개선을 이뤄나가지 않으면 훗날 지금보다 더 큰 이자를 내고 있을 것이다.  