##컴퓨터는 왜 0과 1로 신호를 전달할까? 
>컴퓨터는 전기 신호로 구성된 논리 회로를 갖는다. 전기 신호가 오면 1 오지 않으면 0으로 간주하여 2진법을 사용한다. 
>
>하지만 왜 2진법이 아닌 10진법, 16진법 등을 사용할 수 없을까?
>이는 전기 회로의 특성상 저항이 있고 따라서 노이즈가 발생하기 때문이다. 만약에 10진법을 사용한다고 가정한다. 0~10v를 사용하여 나타낼때, 만약에 신호가 저항/노이즈의 발생으로 인해 3.6v로 온다고 한다면, 이를 반올림해서 4v로 간주한다며 이를 확실한 값이라고 보기 어렵기에 문제가 발생하게 될 수 있다. 따라서 더 정밀하게 측정하기 위해 설계를 더 세세하게 한다거나, 측정 시간이 길어지게 되면 결과적으로 비용이 더 많이 발생하게 된다. 따라서 신호의 유무를 사용하는 것이 훨씬 확실하기 때문에 2진법, 0과 1일 사용하는 것이 기술적으로 더 구현하기 쉽고 용이하다. 



##웹 표준과 웹 접근성
>- 웹 표준: "world wide web의 측면을 서술하고 정의하는 표준이나 다른 기술 규격을 가르키는 일반적인 용어이다." - [위키](https://ko.wikipedia.org/wiki/%EC%9B%B9_%ED%91%9C%EC%A4%80)
>
> 다시 말해, web의 구성에 대한 표준을 말하는 것이다. 올바른 html, css, javascript문법으로 페이지가 작성되었는지에 약속이라고 생각할 수 있겠다. 따라서 웹개발과 웹디자인도 이에 영향을 받고 있다. 또한 이렇게 표준을 정하고 따름으로 인터넷/네트워크 관리에도 직접적인 영향을 주고 있다.
> 
>- 웹 접근성: "장애인, 노인 등 정보취약계층이 인터넷 상에서 차별없이 다른 사용자와 동등하게 정보에 접근하고 이해할 수 있도록 보장하는 것으로 웹 접근성의 주 목적은 웹 콘텐츠를 이용하는 데에 어떠한 상황이나 환경에 구애받지 않고 접근할 수 있도록 하는 것입니다." - [한국웹접근성평가센터](http://www.kwacc.or.kr/WebAccessibility/Definition)
>
> 다시 말해, 웹에 대한 접근성이란 웹상의 정보와 콘텐츠 이용에 있어 장애인과 노인을 포함한 모든 사람들이 차별받지 않고, 쉽게 접근하고 이용가능하도록 보장하는 것이다. 
> 
> 웹접근성을 구성하는 요소로는 1. 콘텐츠 2. user agent(웹브라우저, 미디어 플레이어)  3. 보조기술(화면낭독 프로그램, 대체 키보드, 등)이 있는데, 이 3개가 모두 잘 조화를 이루어 웹접근성을 모두에게 가능하게 하는 것이 중요하다. 

###국내외 웹 표준과 웹 접근성의 현상황
> 우리나라는 안타깝게도 웹표준을 많이 어기고 있는 상황이다. 이로인해 웹호환성에 치명적인 문제를 갖고 있어 익스플로어에서만 작동되는 웹이 상당수다. activeX를 너무나도 좋아해서 항상 익스플로어를 사용하여 금융사 사이트, 관공서를 이용할 수 밖에 없다. 이로 인해 해외에서 우리나라의 사이트를 통해 물건을 살 수 없어 온라인 쇼핑 산업에 영향을 끼치기 까지 한다.  2010년 즈음 부터 개선을 하자는 말은 나오지만 실질적으로 매우 느리게 진행되고 있는 상황이다. 
> 이는 웹접근성과도 연결지을 수 있다. 복잡한 플러그인 설치 등 표준을 따르지 않기에 웹접근성마저 어려운게 현실이다. 장애인에 초점을 맞춘 웹접근성 규제들이 있지만 웹접근성이란 장애인 뿐 아닌 모든 사람이 대상인데 표준을 어기면서 웹접근성을 보장하겠다는 것은 아이러니가 아닐 수 없다. 









