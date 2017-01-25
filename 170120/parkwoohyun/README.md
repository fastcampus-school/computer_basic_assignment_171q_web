##HTTP와 HTTPS의 차이점
>HTTP - HyperText Transfer Protocol
>HTTPS - HyperText Transfer Protocol over Secure Socket Layer   
>둘다 하이퍼텍스트 문서를 전송하기 위한 통신 규약이고 차이점은 HTTPS는 SSL(Secure Socket Layer)를 사용하느냐 안하느냐의 차이이다.
>
>HTTP는 하이퍼텍스트 문서를 클라이언트(웹브라우저)가 웹서버에 요청하는데 그 정보를 일반 텍스트로 전송하는 프로토콜이다. 일반 텍스트이기 때문에 누군가 네트워크 상에서 정보를 빼돌릴 경우 그 내용이 여과없이 다 보여지게 된다.   
>HTTPS는 기본적으로는 HTTP와 같지만 모든 내용을 암호화 한다. 암호화 방식은 비대칭형 공개키 인프라 (PKI) 시스템을 이용한다. 이 암호화 방식은 공개키와 개인키로 구성되어있고 공개키로 암호화 한 데이터는 개인키로만 복호화 할 수 있다. 클라이언트는 공개키만 가지고 있고 웹 서버에서 개인키를 가지고 있기 때문에 해커가 중간에 가로채더라도 개인키를 모르기 때문에 복호화 할 수 없다.



##공인 인증서가 생긴 배경과 그 위험성
**생긴 배경**
>1999년 전자서명법이 발효되면서 인터넷 뱅킹과 전자 상거래를 할 있도록 하기위해 만드어진 것이다. 1995년부터 SSL기술이 있었지만 미국 정부의 정책으로 SSL-40bit이상을 사용 할 수 없었기 때문에 ActiveX를 활용한 공인 인증서가 우리나라 인터넷 금융거래의 주류가 되었다.


**위험성**
>1.은행을 이용하는데 사용자는 직접 본인인증을 해야하고 피싱사이트 인지 확인도 사용자가 직접해야하기 때문에 은행은 책임을 회피할 수 있다.
>
>2.공인 인증서는 세계 표준기술이 아닌 우리나라에서만 사용하는 기술 이기때문에 Active X를 사용해야하고 오랫동안 사용했기 때문에 다른곳이 Active X를 사용하지 않을때에도 다른 기수레 접목할 생각을 하지 않았다. 또한 금융업계는 공인인증서라는 보안에 신경썼기때문에 금융사고에 대한 책임에서 벗어나려고하는 문제를 가지고있다.