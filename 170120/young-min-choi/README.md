#3일차 숙제 by 최영민
####Index
<span style="font-size:18px;"> 1. HTTP/HTTPS 차이 </span>

<span style="font-size:18px;">2. 국내에 공인인증서가 생긴 배경과 그 위험성은? </span>

####참고자료 
[인포피아닷컴](http://infofia.com/?p=133)
[신정훈블로그](http://misako.co.kr/articles/HttpVSHttps.aspx)
[instantssl](https://www.instantssl.com/https-tutorials/what-is-https.html)
[Quora](https://www.quora.com/What-is-the-difference-between-HTTP-and-HTTPS)
[it동아](http://it.donga.com/17704/)

 ---
 
####1. HTTP와 HTTPS?

기본적으로 HTTP는 Hyper Text Transfet Protocol의 약자로서, response-request server-client model에서 client와 server가 image, text, graphic등을 서로 보내기 위한 규약이다. 

인터넷을 하다 보면 여러 protocol을 만나게 되는데 각각이 무엇인지 정확하게 집고 넘어가보자. 
```
HTTP: The Hypertext Transfer Protocol (HTTP) is an application protocol for distributed, collaborative, hypermedia information systems.[1] HTTP is the foundation of data communication for the World Wide Web.

TCP/IP: The Internet protocol suite is the conceptual model and set of communications protocols used on the Internet and similar computer networks. It is commonly known as TCP/IP because the original protocols in the suite are the Transmission Control Protocol (TCP) and the Internet Protocol (IP).
```
둘의 차이점은 TCP/IP는 transport계층에서 활용되는 것인 반면, HTTP는 application 계층에서 활용된다는 것이다. 

가장 인기있는 인터넷 서비스인 WWW, EMAIL, TELNET, FTP등 대부분이 TCP/IP 기반에서 만들어져있다. 인터넷으로 연결된 수많은 컴퓨터와 통신을 위해서 TCP/IP를 선택한 이유는 그 개방성에 있다. 즉 하드웨어, 운영체제, 접속매체에 관계없이 동작할수 있다는점때문에, 인터넷 통신을 위한 핵심으로 선택되었다.

HTTPS는 HTTP Security의 약어로서, 여기서 Security는 Security Socket Layer(SSL)를 나타내는 것이다. 이는 HTTP의 경우 클라이언트와 서버가 통신하는 과정에 존재하는 보안의 허점을 보완한 것이다. 즉 클라이언트와 서버가 통신하는 과정에서 암호화가 필요한데, HTTPS는 공개키, 개인키라는 개념을 통해 이를 해결한다. 

key based encryption algorithm을 이용한다. 

---
#### 2. 국내에 공인인증서가 생긴 배경과 그 위험성은?

- 공인인증서란? 

공인인증서는 쉽게 말해 전자 인감도장이다. 그 종류로는 범용 인증서와 금융거래용 인증서가 있는데, 개인이 본인의 신분을 밝히기 위한 것으로 SEED등 40년이 넘은 알고리즘 방식의 암호화를 채택한다. 40년 넘은 알고리즘을 사용하는 이유는 보안업계가 새로운 알고리즘을 선호하지 않는 보수성이 있기 때문이다. 

- 국내에서 공인인증서가 채택된 배경 

초기 인터넷 웹환경에서 강력한 보안환경을 구축할 방법이 없었다.  https는 SSL방식의 암호화를 제공하나 이는 금융거래로 이용하기에는 취약하다. 그렇기 때문에 한국에서 독자적인 암호화 방식을 개발해야 했으며 그 결과가 공인인증서이다. 

- 문제점 

	1. 공인인증서를 설치하기 위한 모듈이 대부분 Active X라는 점에 있다. 공인인증서의 암호화체계인 SEED는 웹표준을 따르고 있지 않기 때문에 이를 설치하기 위해서는 추가적으로 Active X가 필요하고, 이는 추가적인 보안허점을 만들어낸다. 

	2. 공인인증서는 서비스 사용자를 인증하는데 사용될 수 있지만 서비스 제공자를 인증하지는 않는다. 그러므로 서비스 사용자는 본인을 증명할 수는 있지만, 서비스를 제공자를 확인할 방도가 없다. 이러한 허점을 이용한 것이 피씽사이트이다. 

	3. 외국인의 경우에도 공인인증서를 받아야만 국내 온라인 쇼핑몰을 이용할 수 있다. 실질적으로 공인인증서를 외국인이 사용하는 것은 거의 불가능하다는 점을 생각했을 때, 이는 외국인의 국내 온라인 쇼핑을 금지하는 것과 마찬가지라고 할 수 있다. 

- 느낀점