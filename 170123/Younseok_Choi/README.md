### 컴퓨터는 왜 0과 1로 신호를 전달할까

초기의 컴퓨터인 애니악의 경우엔 10진수를 사용했었다. 하지만 연산상의 문제로 인한 고열 발생, 연산처리 능력 저하, 컴퓨터의 부피 증가 등의 문제점 때문에 다른 방법을 모색하게 되었는데, on/off로 동작하는 전기 신호의 조합인 컴퓨터 내의 정보를 표현하는데 2진수는 딱 맞는 구조였다.

주변에서 흔히 볼 수 있는 전자 제품에 on/off개념이 있듯이 집적 회로도 on/off 형식으로 동작한다. 전압을 가하면 on이 되고 가하지 않으면 off가 되는데, on 은 1을 off 는 0을 의미하도록 하여 2진수로 표현하는 것이다.

| on(전압을 가하면)      | 1    |
| :--------------- | ---- |
| off(전압을 가하지 않으면) | 0    |



### 웹 표준과 웹 접근성

#### 웹 표준과 웹 접근성

웹 접근성이란 월드와이드웹을 창시한 팀 버너스 리의 말을 다시 한번 곱씹어보면 잘 알 수 있다.

> 장애에 구해 없이 모든 사람들이 손쉽게 정보를 공유할 수 있는 공간

웹 콘텐츠를 제작할 때에는 장애에 구애됨이 없이 누구나 접근할 수 있도록 제작하여야 한다. 그러나 접근성을 장애인에게 국한된 문제라고 하는 것은 이 단어를 너무 미괄적으로 보는 것이다.

비록, 접근성 준수가 장애인에게 가장 혜택이 많이 돌아가는 것은 사실이다. 그러나 접근성은 장애인 뿐만 아니라 모든 사람이 정보통신 기기나 서비스 손쉽게 활용할 수 있도록 만드는 것을 말한다. 예를 들면 장애인과 노인들을 위해 개발된 리모콘, 전화, 자동문 등이 제품들이 널리 보급되면서 궁극적으로 모든 사람들이 편리하게 활용하게 된 것을 들 수 있다.

웹 접근성을 지키면서 웹페이지를 만든다는 것은 소스코드에 내용을 텍스트로 담는 것을 권장한다. 왜냐면, 만약 해당 정보를 읽을 수 없는 상황의 유저인 경우, 스크린 리더기능을 활용하여 텍스트에 담긴 내용을 들을 수 있기 때문이다.

W3C에서 제정한 웹 접근성은 다음과 같다.

- 원칙 1: 인지 가능성
  정보와 사용자 인터페이스 구성물은 사용자가 인지할 수 있는 방식으로 제공돼야 한다.

- - 1.1. 텍스트가 아닌 콘텐츠가 있을 경우 이를 텍스트로 이루어진 대체 콘텐츠와 함께 제공해야 한다. 이는 대체 콘텐츠를 확대된 이미지, 점자, 음성 메시지, 기호, 더 간단한 언어로 바꾸어 필요한 사람에게 전달하기 위해서이다. 

  - - 1.1.1. 텍스트가 아닌 콘텐츠: 텍스트가 아닌 콘텐츠는 동일한 목적을 수행하는 대체 텍스트와 함께 제공돼야 한다.

    - - 상황 1: 입력 및 제어 
        텍스트가 아닌 콘텐츠가 사용자가 무언가를 입력하거나 작동시키는 기능을 한다면 그 콘텐츠의 기능을 설명한 이름을 반드시 붙여주어야 한다. 
      - 상황 2: 시간에 기반한 미디어 
        텍스트가 아닌 콘텐츠가 시간에 기반한 미디어(사전 녹음된 음성, 사전 녹화된 비디오, 생방송 등)일 경우, 콘텐츠에서 보여지는 상황을 설명하는 대체 텍스트가 반드시 포함되어야 한다. (예: 자막)
      - 상황 3: 테스트 
        텍스트가 아닌 콘텐츠가 시험이나 연습의 형태인데 텍스트로 보여지면 제 기능을 수행할 수 없을 때는 그 콘텐츠를 무엇인지 설명하는 대체 텍스트가 반드시 포함되어야 한다. 
      - 상황 4: 인식 센서
        텍스트가 아닌 콘텐츠가 사용자의 어떤 행동을 인식하는 센서 기능을 한다면 그 콘텐츠를 설명하는 대체 텍스트가 반드시 포함되어야 한다. 
      - 상황 5: [CAPTCHA](https://namu.wiki/w/CAPTCHA)
        텍스트가 아닌 콘텐츠가 반드시 컴퓨터가 아니라 사람에 의해 인지되고 판단되어야 한다면 그 콘텐츠의 기능과 목적을 설명하는 대체 텍스트가 반드시 포함되어야 한다. 그리고 장애인도 인식할 수 있도록 별도의 방식으로 전달하는 대체 CAPTCHA를 같이 제공해야 한다. 
      - 상황 6: 디자인상 꾸미기, 보이지 않아야 하는 콘텐츠
        텍스트가 아닌 콘텐츠가 온전히 디자인을 더 좋게 하기 위한 목적에서 쓰인다면, 혹은 사용자에게 보이지 않아야 하는 콘텐츠라면 장애인이 이용하는 보조 도구가 이를 인식하지 않고 무시할 수 있도록 만들어야 한다. 

  - 1.2. 시간에 기반한 미디어(사전 녹음된 음성, 사전 제작된 영상, 생방송 영상)가 있을 경우 이와 함께 대체 콘텐츠를 제공해야 한다. 

  - 1.3. 제공해야 하는 정보를 온전히 전달하고 필요한 구조를 온전히 유지하는 선에서 더 간단한 레이아웃으로 사용자에게 전달할 수 있도록 콘텐츠를 만들어라.

  - 1.4. 배경에서 내용물을 분리해내는 것을 포함해 사용자가 콘텐츠를 보거나 읽는 것을 더 쉽게 해낼 수 있도록 만들어야 한다. 

- 1. 작동 가능성

- - 오직 키보드만으로 모든 기능을 사용할 수 있도록 해야 한다. 
  - 사용자가 콘텐츠를 읽을 충분한 시간을 제공해야 한다. 
  - [사용자가 신체적 발작을 일으킬 가능성](https://namu.wiki/w/%EB%8B%8C%ED%85%90%EB%8F%84%20%EC%A6%9D%ED%9B%84%EA%B5%B0)이 있는 방법으로 콘텐츠를 제작하지 말아야 한다. 
  - 사용자가 웹페이지를 살펴보고, 필요한 내용을 찾고, 지금 어느 부분을 보고 있는 것인지 알 수 있도록 해야 한다. 

- 1. 가독성

- - 텍스트로 이루어진 콘텐츠를 읽을 수 있도록, 이해할 수 있도록 만들어야 한다. 
  - 웹페이지가 사용자가 예측할 수 있는 방향으로 보이고 작동하도록 만들어야 한다. 
  - 사용자가 실수를 피할 수 있도록, 그리고 고칠 수 있도록 해야 한다.

- 1. 호환성

- - 장애가 있는 사용자를 위한 보조 기술을 포함해, 최신 기술 그리고 앞으로 사용될 기술과 호환 가능하도록 만들어야 한다. 

웹 표준

웹 표준은 간단히 말해서 웹사이트의 '산업표준'이라고 말할 수 있다. 같은 코드라도, 웹 브라우저마다 호환이 되지 않아 웹페이지가 브라우저마다 다르게 보여지게 되었다. 그래서 웹페이지 제공 업체들은 브라우저마다 호환을 높이기 위해 각각 브라우저마다의 페이지를 따로 만들게 되었다. 우리나라의 경우엔 인터넷 익스플로러가 얼마전까지 대세였기 때문에 익스플로러를 기준으로 왠만한 사이트가 설계되었었다. 

그러나 이렇게 브라우저마다 페이지를 달리 만들어야 되는 수고스러움이 심했기 때문에 W3C와 국제 인터넷 표준화 기구등이 모여서 웹브라우저 제공 업체들에게 웹 표준을 만들어 지켜달라고 요청하였다.



#### 국내의 웹 표준과 웹 접근성의 현 상황

국내의 표준 현황은 대형 포탈부터가 액티브 엑스를 요구하였다. 물론 지금은 스마트폰의 보급으로 별로 찾아볼 수 없지만, 몇 년전까지만 하더라도 엑티브 엑스가 없으면 제대로 된 웹페이지를 볼 수 없었다.

그리고 국내 은행이나 쇼핑몰의 경우엔 엑티브 엑스가 없으면 제대로 된 쇼핑이나 뱅킹을 사용할 수 없다. 심지어 정부 사이트는 더욱 심하다. 엑티브 엑스를 통해 벼래별 미친 플러그인을 깔아야지 사용할 수 있다. 겪어본 중 최악은 관세청이다. 관세청을 사용하기 위해선 매직패스라는 말도 안되는 플러그인을 설치해야되는데 이는 유니패스를 사용하지 않더라도 꺼지지도 않고 계속해서 상주해서 메모리를 갉아먹는다. 

그 다음은 국회 도서관이다. 파쏘라는 말도안되는 pdf뷰어 플러그인을 설치해야되는데 이 역시도 미친듯이 상주해있다. 심지어 삭제하기도 정말 어렵다. 

국가사이트부터가 웹표준 접근성을 지키지 않는데 뭔놈에 다른 일반 사이트에 표준을 바라는가. 한참 멀었다. 아오..