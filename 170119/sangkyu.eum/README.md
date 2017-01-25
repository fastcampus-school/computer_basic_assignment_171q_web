## Active X

#### active x 가 뭐에요?
* 근본적으로는 Microsoft에서 만든 COM(component object model)과 OLE(object linking and embedding) 기술을 합친 software framework를 의미한다.
* 다만 한국에서 일반적으로 말하는 active X는 IE에서 add-on으로 실행되는 "Active X Control"을 의미한다. 일반적인 웹 브라우저의 역할을 넘어선 여러가지 기능을 수행할 수 있게 해주는데, 예를 들어 컴퓨터 내에 파일을 생성하거나 레지스트리도 수정할 수 있게 할 수 있다. 이를 통해서 각종 다운로드 서비스, 게임 실행, 음악 재생 등과 같은 다양한 프로그램을 웹페이지 접속만으로 실행할 수 있는 기능을 제공하면서 웹페이지 사용을 더욱 풍요롭게 해주었다(고 생각했다.)

#### 근데 왜 문제가 되나요?
* 맥이나 리눅스를 쓰는 사람은 대한민국사람 아닌가요?
	- active x는 IE에서만 거의 정상적으로 지원하며, 웹 브라우저 안에서 윈도우즈 실행파일(.exe)을 실행시키는 것이기 때문에 윈두우즈가 아닌 다른 OS에서는 실행이 불가능하다. 또한 같은 윈도우즈라도 다른 웹브라우저를 사용할 경우, 해당 페이지가 제대로 표시되지 않는다. 게다가 상위 IE 버전에서는 active x의 작동이 제한됨으로써 윈도우즈 사용자마저도 사용에 불편함을 겪고 있다.
* 악성코드의 온상
	- 일반 사용자가 active x를 설치하라는 안내가 나오면 습관적으로 'yes'를 선택하며 쉽게 확인하기도 힘들다. 결국 active x를 통해서 악성코드가 쉽게 퍼지게 되는 가능성이 매우 높아졌다.

#### 안 좋은데 왜 아직도 써요?
* 공공사이트, 금융거래...
	- 본인인증이 필요한 경우, 우리나라에서는 공인인증서를 주로 사용하는데 여기에 무조건 active x가 들어간다. 사실 active-x가 계속하여 애용하는 이유는 책임을 피하기 위해서이다. 사용자 부주의(백신 미사용 등)으로 해킹 등의 금융사고가 발생한다 하더라도 웹사이트를 운영하는 금융권 쪽에서 책임을 져야 하는 조항이 있으며, 금융 사고 예방책으로 사용자에게 보안 프로그램을 제공해야 하는 의무가 있는데 이 보안 프로그램들이 전부 active x 기반이다. 
	- 결론적으로 단순히 웹브라우저를 넘어서 모바일 기기가 대중화되어 있는 현재, 타 OS를 지원하지 못하는 <b>최저의 범용성</b>, 무조건 다운로드받도록 하여서 악성코드가 쉽게 퍼질수 있게 하고 시스템에 여차하면 쉽게 접근 가능할 수 있는 통로를 제공해서 좀비pc로 만들 수 있는 <b>최저의 보안성</b>을 만들어내는 이른바 한국 인터넷의 "악의 근원" 중 하나이다.

##Technical Debt
> 기술 자본이 많지 않은 집단이 빠르게 기술력을 개발하기 위해 포기하는 많은 것들이 결국에는 debt(부채)로 돌아온다는 것

* 현 시점에서 쉽고 빠르게 (하지만 지저분하게) 기술을 만들어내면 회계적 부채와 같이 지속적 추가 개발 노력이라는 이자를 내야 하는 것이다. 이자를 계속 내면서 부채를 유지할 수 도 아니면 기존의 설계를 리팩토링을 통한 개선을 실시하여 원금과 이자를 함께 상환할 수 도 있겠다.

* active x도 처음 나왔을 때는 간단한 add-on 실행을 통해 다양한 프로그램을 웹브라우저에서 실시하면서 사용자와 개발자 모두에게 굉장한 이익을 주었다. 다만 시간이 흘러가면서 부정적인 부분이 많이 발견되었고, 이 과정에서 "원금과 이자를 차근차근 상환"하기는 커녕, 이자가 점점 커져서 원금은 물론 이자 내기도 힘들어진 상황에 온 것이다...

* 그런데 자본주의 사회에서 빚은 good/bad로 나뉠 수 있는 종류의 문제가 아니다. 지금 당장 부채를 발생시키더라도 미래의 현금을 현 시점으로 미리 가져와서 투자해서 그 이상의 이익을 발생시켜 결과적으로 이익을 취할 수 있다면 보다 큰 성장을 할 수도 있는 것이다.

* 기술 부채를 발생시킬 것인가의 문제는 다음 두 가지를 비교해야 한다.
	- '기술 부채'로 발생하게 되는 비효율의 크기
	- 당면한 비즈니스 기회의 크기
* 두 가지를 정확하게 비교하여 결정하는 것은 결코 쉽지 않은 일이다. 따라서 이 결정을 위한 개발자의 정확한 상황 판단 및 의사 결정이 빠르게 발전하는 현 시장에서 그 무엇보다 중요하다.

##epilogue.
* 빠듯한 일정, 급격한 요구 사항 변경, 팀의 숙련도 부족, 빈약한 문서, 테스트되지 않은 코드, 반복되는 수동 배포, 미뤄진 리팩토링...을 피하자.
* 단순히 코드만 짜는 개발자는 필요없다.

 