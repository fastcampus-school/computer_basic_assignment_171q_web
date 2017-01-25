#Active X
##What is Active X
자칭 IT강국, 내가 보기에는 인터넷만 빠른 나라, 대한민국의 발전을 막는 악의 축 중의 하나이다.

실제로는 다른 의미가 있다고 하는데 일반적으로는 IE에서 애드온으로 실행되는 응용프로그램이다.  
용도에 따라 온갖 종류가 있기 때문에 Active X란 정확히 이럴 때 쓰인다라고 정의내리기가 어렵다. 그나마 할 수 있는 말이라고는 "IE에 추가기능 붙여쓸 때 설치하는 것"이란 것이다. 여기까지는 일반적인 애드온과 크게 다를 바 없는 듯하지만 Active X는 자신만의 아주 특별한 특성들이 있다. 그리고 그것들이 문제다.
###Problems of Active X
1. 너무 많은 권한이 주어진다.
	* 내가 생각하는 Active X를 쓰지 말아야할 첫 번째 이유이다. IE를 쓰기 위해 쓰는 응용프로그램 주제에 PC의 로컬파일이나 레지스트리 등도 제멋대로 손댈 수 있다. 아무 생각없이 [예]를 눌렀다가는 PC 어딘가에 무엇이 설치되거나 삭제될지 모른다. 심지어 로컬이벤트 정보마저 읽어서 어딘가로 보낼 수 있는데다가 이런저런 기능들이 사용자의 의사와 관계없이 자동으로 실행될 수마저 있다. 보안관계상 참으로 무서운 일이 아닐 수 없다.
2. 특정 버젼에 특화되어 있다.
	* 시대에 걸맞지 않은 특성이라 할 수 있다. IE 버젼에 따라 다른 Active X를 설치해야한다. 만일 내가 IE를 업데이트했을 때 원래 있던 Active X를 업데이트하는 수준에 머물러 있다면 그나마 양심적일텐데 그것도 아니고 새로 설치해야 한다. 오호 통재라. 그러면 적어도 저번 버젼은 삭제해주는 배려는 발휘해주었으면 하는 바이지만 그런 적이 있었나 싶다.
3. 내가 사겠다는데 왜 팔지 않니!
	* 세상에 많고 많은 모든 웹브라우져를 지원할 필요는 없다. 하지만 적어도 메이져 브라우져들에는 사용할 수 있도록 해야하는 것 아닌가? 대한민국 국민이라면 누구나 결제창까지 갔는데 IE가 아니라고 결제를 할 수 없는 경우가 있었을 것이다. 최근 몇년간은 이런저런 다른 방식으로 결제가 가능하거나 크롬, 파이어폭스 등은 가능하게 되기는 했다만 이것은 어디까지나 메이져한 예시일뿐이지 Active X는 다른 기능으로도 많이 쓰인다.
4. 설치시 IE 강제 종료
	* 정말 끔찍한 일이다. 모든 과정을 다시 돌아가 진행해야 한다.
5. Active X끼리 충돌
	* 같은 Active X라면 하나만 설치하면 될 것을 Active X를 쓰는 사이트마다 자기 사이트에 맞춘 다른 버젼을 쓰고 있다. 어이없는 점은 분명 같은 회사에서 만든 버젼만 다른 Active X인데 이것들끼리 서로 충돌을 일으키기도 한다.
6. 컴퓨터가 느려진다.
7. 기타 등등
	
##Why in ROK
SEED라는 이름의 "한국형" 암호화 알고리즘이 원인이다. 인터넷 뱅킹을 위해 필요한 암호화 알고리즘을 옛날옛적에 주로 쓰이던 IE에 적용하기 위해 어쩔 수 없이 Active X를 쓰게 되었다. 당시에는 좋은 석택이었지만 추후에는 대한민국 인터넷 뱅킹 및 거래의 발목을 잡게 되었다.
##Technical Debt
개발 중 모자란 부분을 놓쳤을 때 차후에 처리해야할 '빚'이 되어 돌아온다는 뜻이다.  
여러 이유로 일어나는데 무리한 시도나 부정확한 요구나 잦은 변경, 팀워크 부족, 문서화를 안 했을 때, 테스팅이 모자랄 때, 설계가 유연하지 않아 추후 변경이나 확장이 어려울 때 등등이 있다.
##Personal Thoughts
나무위키 따위에게 물어보게 될 줄은 몰랐다. 특히 Active X는 쓰다가 조금 열 받았다.