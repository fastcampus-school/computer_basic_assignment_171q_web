###1. 컴퓨터는 왜 0과 1로 신호를 전달 할까?

* 영국의 수학자 앨런 튜링은 테이프에 적힌 여러 가지 기호를 일정한 규칙에 따라 기호로 바꾸는것을 고안 하였다. 정보를 0과 1로 구성되어 있더라도 일정한 알고리즘만 있다면 어떤 계산도 가능 할것이라고 생각 했다.
* 이런 튜링은 영감은 1931년 미국의 수학자 쿠르트 괴델의 '불완전성 정리에서 영감을 받았다고 알려졌다
* 처음 컴퓨터가 고안 되었을 때는 전기 신호의 on/off에 따라 이진법을 사용 하였고, 기술이 발전 함에 따라 전기 신호의 on/off를 다루는 회로가 축소되고 정밀화 되었다
* 기술이 발전 함에 따라 전기신호의 세기에 따라 이진법이 아니라 2진법 이상의 수체계를 가질려고 했으나, 전기 신호의 불완전한 전달과 수치 측정으로 기술적 어려움을 가지게 되었고
* 2진법을 사용하더라도 같은 작업을 반복과 저장매체에 기록과 출력에는 문제가 없었기 때문에 계속해서 0과 1의 이진법을 사용하게 되었다.


###2. 웹 표준

* 과거 역사를 보게되면 변방의 작은 나라를 침약하여 통합해서 나라가 개국 하였을 때 가장 먼저 시행하는 정책이 도량형의 통일이다.
* 도량형의 통일은 유통 등의 상거래의 기준이 되기도 하는데, 사람들의 사용하는 단위를 통일시켜 혼란을 방지하고자 하는게 가장 크다고 할 수 있다. 
* 우리도 예전에는 집의 크기를 '평'이라는 단위를 사용 하였지만, 이제는 제곱미터 단위로 변경 하였는것과 마찬가지다. 
* 인터넷이 대중화 되고나서도 http 프로토콜을 사용하는 www에서 이 표준이 정립되지 않고 혼용 되던 기간이 있었다.
* 사용하는 기기와 시스템 운영체제에 따라 다른 기준에 따라 코딩을 해야 하는 경우가 발생하고, 한 기기에서 정상작동하지만 다른 기기에서는 정상 작동하지 않아, 같은 정보를 두개로 표현하는 기술 낭비 시절이었다.
* 현재는 이러한 문제점을 해결하기 위한 Html 표준이 등장 하였고, 이 표준을 제정하는 여러기구가 생성 되었다.
* 현재는 Html5가 웹표준으로 지정 되었으며, 그 세부 사항에 대한 약간의 지식이 필요 하다. 

> HTML이란?

>Html은 인터넷 서비스의 하나인 월드 와이드 웹(www)을 통해 볼 수 있는 문서를 만들 때 사용하는 프로그래 밍 언어의 한 종류이다. 특히 하이퍼텍스트를 작성하기 위해 개발 되었으며, 인터넷에서 웹을 통해 접근되는 대 부분의 웹페이지들은 html로 작성된다 (두산백과 참조)

>1) 최초의 웹페이지는 1990년 영국의 과학자인 팀 버너스리에 의해 만들어졌으며, 동시에 웹브라우저도 직접 제작하였으며 이 때 사용된 웹브라우저의 이름이 월드와이드웹(www)이다.

>2) 그리고 1991년에 이를 대중적으로 공개하며 사용된 문서를 ‘HTML 태그’라고 부르면서 HTML이 시작

>3) 1994년에는 웹의 기능을 좀 더 발전시키기 위해 W3C가 만들어졌으며(W3C - ‘World Wide Web Consortium’, 웹 표준을 만들고 다양한 분야에서 표준에 맞게 사용할 수 있도록 지원하는 조직)

>4) 1995년에 HTML 2.0이 나왔으며

>5) 1999년 현재의 HTML 4.01 등장

>6) 2004년 오페라, 모질라 재단, 애플이 주축이 되어 별도의 HTML 표준안을 만들기 위한 조직을 구성하여 HTML5 작업 진행

>7) 2014년 HTML 최신 표준으로 HTML5 확정

>HTML5 등장 배경

>1) 플랫폼의 다양화 : 윈도우 PC의 독점적 인터넷 환경에서 모바일 등의 다양한 플랫폼이 등장함에 따라 호환성 문제가 발생하여 모든 플랫폼을 지원 할 수 있는 필요성의 대두

>2) 웹서비스 수요의 패턴 변화 : 고속 인터넷망 구축에 따라 텍스트 위주의 웹서비스에서 멀티미디어 및 유저

>상호 반응에 따른 환경의 대두하고, 기존 html4에서도 서비스를 제공 하였지 만 특정 플랫폼에서만 원활히 지원되고, 서비스 제공시 복잡한 외부 플러그인 을 필요하였음.

###3. 웹 접근성

* 웹 접근성이란 '보다 많은 사람이 이용 할 수 있도록 웹페이지를 구성하여, 모든 사용자가 신체적 환경적 조건에 구애 없이 웹에 접근하여 이용할 수 있도록하는 것'을 뜻한다. 

* 웹 접근성의 예로는 저시력자를 위해 이미지보다는 txext로 웹을 구성하고 글자 확대 기능을 구현 하는 방법
* 다양한 모니터 해상도를 고려하여 반응형 웹을 제작하는 방안
* 또한 난독증을 가진 사람을 위해 콘텐츠를 TTS등의 기능을 구현하여 탑재하는 것들이 있다.
* 웹 접근성 또한 표준적인 지침이 있는데, 그 지침은 W3C에 다음과 같다

> 1. 인지 가능성
> 정보와 사용자 인터페이스 구성물은 사용자가 인지 할 수 있는 방법으로 제공
> 2. 작동 가능성
> 키보드로 모든 기능을 사용 할 수 있어야 하며, 사용자가 컨텐츠를 활용 할 충분한 시간을 제공해야 한다.
> 3. 가독성
> 텍스트로 이루어진 콘텐츠를 읽을 수 있어야 하며, 사용자가 예측 할 수 있는 방향으로 보이고 작동해야 한다.
> 4. 호환성
> 장애가 있는 사람을 위한 보조 기술을 포함해야 하고, 앞으로 사용 될 기술과 호환 할 수 있어야 한다. 

###4. 국내외의 웹 접근성과 웹 표준의 현황

* 미래창조과학부에서는 2015년 정보접근성 실태조사라는 항목으로 웹접근성과 비슷한 조사 결과를 발표 하였다. 

> 정보접근성 대상 사이트는 대중성이 높다고 판단한 웹사이트 100개 모바일 앱 50개 및 민간기업 대상으로 총 800개 사이트를 조사하였다고 함

> 조사결과를 요약 하면, 웹사이트 점수는 83.2점 모바일 앱은 78.1점으로 2013년 이후로 꾸준히 개선 되고 있다고 한다.

> 조사 분야별로 나누면, 민간법인 82.5점, 의료기간 85.2, 복지시설 83.1, 방송언론 77.2점이며

> 대중성이 높은 사이트(랭키닷컴 기준 100위 사이트) 웹사이트 78.9점, 모바일 77.9점이다. 

> 웹과 모바일 앱에서 공통으로 미흡한 부분으로는 '대체텍스트'라고 한다.

* 웹 표준 준수에 대한 신뢰 할 수 있는 자료는 파악 하지 못하였으나, 현재의 관공서와 금융권 등의 사이트 형태를 보면 파악하지 않아도 엉망이라는것을 알 수 있다.
* ActiveX는 웹 표준이 절대 아님에도 관공서와 금융권 홈페이지는 ActiveX 없이는 이용 할 수 없기 때문이다. 