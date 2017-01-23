## 0 & 1
* 컴퓨터는 왜 이진법을 사용하게 되었을까?
	* Part 1. Based on mathmatics
		1. 라이프니츠
		
			> 0과 1만으로도 세상 모든 숫자들을 표현할 수 있다. (이진법)
		2. 부울
		
			> x 이면 y 이다. <br> 다시 말해서, x=1 이면 y=1이다. 따라서  x(1-y)=0 이다. <br> 이 말은, x 이면서  y가 아닌것(1-y)은 거짓이다.<br> xy=1 이다.  (부울대수, 수학에 기초한 논리표현법)
		3. 프레게
		
			> ![image of frege logic](https://qph.ec.quoracdn.net/main-qimg-ea9bcef4a8f08ad3b5fefa95d5f1a37d?convert_to_webp=true)
			
			> 기호를 사용한 논리적인 수량표현 가능
		
		4. 칸토
		
			> 1. 자연수와 분수들을 일대일 대응(매핑)시켰음. 분수가 더 많은 거 같지만 자연수와 분수 모두 무한집합이기 때문에 이것이 가능.<br> 예를 들어 1/1은 1에 매핑. 1/2는 는 분자 분모의 합이 3이며 같은 합을 가진 다른 분수는 2/1이 있다. 그러므로 1/2 는 2에 매핑. 2/1은 3에 매핑할 수 있다. 이런 방법과 유사하게 모든 분수들을 매핑시킬 수 있다. 
			
			> 2. 더욱 중요한 사실은 자연수로는 실수와 일대일 대응이 불가능하다는 사실이다. 예를들어 1/3을 실수로 표현하면 0.333333... 이 된다. 칸토는 대각선법칙을 통해 이러한 사실을 증명했는데 이러한 이유때문에 컴퓨터에서는 실수부분에서 오차가 생기는...건가?!?
		5. 힐베르트
		
			> 1+1=2 라고 정의하자.<br>
			만약 1 -> 999, + -> 505, = ->698, 2 -> 998 <br>
			그렇다면 위의 식은 다음과 같이 표현될 수 있다.<br>
			999505698998<br>
			즉, 부호화된 수식을 사용하여 새로운 수학체계를 만들 수 있다는 점.
			
		6. 괴델
		
			> based on, 힐베르트 프로그램 <br>
			"A 라고 하는 수학적인 가상의 영역이 있다고 하자.<br>
			A 영역 안에서 공간자체에 모순이 없다면,<br>
			A 내에서는 모순된 결론은 절대로 나오지 않도록 설계되어졌다."<br>
			이 프로그램에 대해서 괴델은 <br>"만약 A 영역에 모순이 없다면 X는 참이다.
			하지만 A 영역내부에서는 X가 참이라는 것을 절대로 증명할 수 없다." 증명<br> 즉, 결정불가능한 명제 존재의 유무 증명.
			
		7. 튜링
		
			> "라이프니츠는 인간 이성을 계산으로 환원하는 것을, 그리고 계산을 실행할 강력한 기계 기관을 꿈꿨다. 프레게는 처음으로 인간의 모든 연역적 추론을 유사하게 설명할 수 있는 체계를 마련했다. 고전수학의 전체영역을 망라하는 러셀의 <수학원리PM>체계에서 괴델은 "PM 조차도 PM 안에서는 증명될 수 없는 진리가 반드시 존재한다는 것을 증명한 "불완전성 정리"를 발표한다. 힐베르트의 결정문제와 괴델의 불완전성 정리에 대해서 배우던 튜링은 힐베르트가 원하는 결정문제 알고리즘이 없다는 것을 어떻게 증명할 수 있는지에 대한 생각을 기반으로 사람이 생각하는 알고리즘을 구현하기 시작했다. 어떤 계산이든 엄격하게 규정된 장치로 실행할 수 있다는 생각과 칸토의 대각선방법론을 활용해서 보편기계를 만들어낸다. 2차 세계대전동안 에니그마를 해독하기 위한 기계설계를 착안해서 '콜로서스'라는 전자식 자동계산장치를 만들어내었다. 이후 발전과정에서 폰-노이만이 집중한 "수칙계산"과 튜링이 집중한 사고체계의 본질적 과정인 "논리적 추론"을 함께 반영한 설계를 기반으로 현대컴퓨터가 발전하기 시작했다.
			
* 컴퓨터는 왜 아직도 이진법을 사용할까?
	* part 2. based on HW/engineering perspective
		- it's because of signal degradation. let's say you have a base-3 system. Anything over base-2, and the only way to differentiate between states is by the strength of the electrical current passing through the circuit. you can't rely on "on" or "off" anyomre. Also every transistor needs to be capable of identifying the signal's level of power, and outputting an appropriate result. As you increase the base, the complexity required increases exponentially.
		- After any amount of use, electrical components will begin to degrade and they could no longer provide proper modulation.
		- We only use binary because we currently do not have the tech to create "switches" that can reliably hold more than two possible states. the binary system was chosen only because it is quite easy to distinguish the presence of an electric current from an absence of it, especially when working with trillions of such connections. 

* 앞으로도 이진법을 쓸까?
	- Quantum computing?
	
		> 예를 들어, 2^n개의 상자가 있고 그 중에 하나에 공이 들어있다고 하자. 공이 들어있는 상자를 확실히 찾기 위해서 <br>
		고전 컴퓨터는 2^n 번 상자를 열면 된다. 반면에 양자컴퓨터는 여는 동작을 하기 전에 2^n개의 n비트 번호들을 양자 중첩 상태로 만들어서 열면 된 것이다. 그런데... 이건 사실이 아니다.<br> 왜냐하면 위와 같은 논리라면 공을 발견할 확률은 기하급수적으로 작은 2^(-n)밖에 되지 않으므로 공을 사실상 찾지 못한다고 주장할 수 있기 때문이다.
		
		> 일반적으로 양자컴퓨터가 더 빠른 결과를 내는 경우는, 잘못된 솔루션들이 서로를 상쇄하는 경우, 대표적으로 인수분해 같은 경우이다. 그런데 현재 보안시스템 알고리즘의 대부분이 소인수분해에 의거하고 있기 때문에 양자컴퓨터라면 현재의 보안 알고리즘은 쉽게 풀어낼 수 있다(고 하지만 "격자 기반" 암호계는 아직 양자컴퓨터로 해결할 수 있는 알고리즘이 없다고 한다..)

## 웹 표준과 웹 접근성

* 웹 표준이 뭐에요?
	- 웹 표준성은 WWW을 정희하는 공식 표준이나 다른 기술 규격을 가리키는 일반적인 용어이다. 즉 같은 웹페이지라면 어느 부라우저를 사용하는지 여부에 상관없이 웹페이지가 똑같이 보이고 정상적으로 작동해야 함을 의미한다. 2016년 현재 인터넷 사용 인구가 30억명을 넘어서고 표준이 없다면 각 브라우저에 맞는 웹 페이지를 작성해야 하는 사회 비용이 증가하는 것이다. W3C의 정의에 의하면 웹 표준성은 접근성, 사생활 보호, 보안, 국제화의 측면을 고려해야 한다.

* 웹 접근성이 뭐에요?
	- 웹 접근성은 장애 여부에 상관없이 누구나 원활하게 웹페이지를 이용할 수 있어야 한다는 것을 의미한다.