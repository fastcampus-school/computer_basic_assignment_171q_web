#Ram
	Ram 은 Random Access Memory의 축약된 글자로 휘발성메모리이다.
	임의 기억장치, 자유기억장치라고 불린다. 보조기억장치에서 저장된 파일을 불러와 메모리에 올려놓고 cpu에 실행 명령을 보낸다. 그래서 cpu는 좋을수록 처리속도가 빨리지고 램은 클수록 여러프로그램을 실행시에 리프레시가 줄어든다. 다다익램! 
	우리나라에는 1999년에 반도체 빅딜이 있었다. 램버스 램을 필두로 하는 lg전자와 현대전자의 인수합병 당시 구본무 회장이 lg전자의 합병문제에 있어서 충격을 받아 전경련 활동도 안한다고했지만 그 당시 lg전자가 반도체 사업부문을 유지했다면 아마도 지금쯤 lg전자는 풍비박산이 났었을 것이다. 이유로는 intel에서 램버스램으로 크게 데이고 d램으로 넘어가던 시기였다... 그래서 램버스 램을 주력 품목으로 하는 lg반도체는 계속남았다면 lg그룹의 머니블랙홀이 되었을것이다. 
	
# 하버드 구조와 폰노이만의 한계
 - 하버드 구조
 	- cpu 코어에에서 공간을 적게 차지한다.
 	기억 장치와 데이터 기억장치를 하드웨어적으로 완전히 분리하여 속도를 높였다.
 	
 - 폰 노이만 구조
 	- 메모리값을 읽고 쓰는 구조이기 때문에 기억장치에서 병목현상이 생길 수 밖에 없다.
 	
 미래 
 2014년에 hp에서 선보인 더머신 폰노이만 아키텍처의 근간을 뛰어넘는 기술을 발표했다.
 폰노이만의 속도문제점을 구리선의 속도한계로보고 광전송으로 바꾸었고 메모리 방식으로  멤리스터 계층방식으로 전환하여 앞으로의 발전가능성을 보여주었다. 
 

#한글 문자인코딩
영어와 유럽의 언어들은 알파벳을 기초로 사용해서 256개의 코드를 이용하여 모든 문자를 표현이 가능하다. 하지만 한중일 이 세나라에서 사용하는 문자 집합은 개수가 워낙 무궁구무진하여 ASCII코드로도 이를 모두 처리할 수 없다. 따라서 별도의 문자를 표한하는 방법이 필요했다. 
###N바이트 조합형 
최초의 한글 표현방식이다. 컴퓨터에서 한글을 사용하기위해 고안된 최초의 인코딩이다.
###3바이트 조합형
초성,중성,종성에 1바이트씩 할당하여 사용하는 방삭이다 .
###7비트 완성형
세운상가에서 만들었다고하여 청계천 한글이라고도 한다. 소문자 뒤에 대문자가오는 경우가 거의 없었고, 특수 문자뒤에 영문자가 오는 경우가 거의 없다는 점에 착안하여 고안한 방식이다. 글자표현이 1300여자로 제한되고 영어단어의 일부가 한글로 표현되는 오류가 있었다.
###2바이트 조합형,2비트 완성형
완성된 글자를 코드와 대응 시키는 방식이다. 완성형으로는 표현할 수 없는 글자가있어 한글 원리를 무시한다는 비난이있었다. 
###확장완성형
MS네서 제정한 문자 집합으로 완성형 코드에서 표현할 수 없었던 8,822자가 추가되었다. 하지만 문자의 정렬에 문제가있엇다.
###한글의 인코딩 방식
EUC-KR은 KS X 1001과 KS X 1003 표준안의 인코딩 방식이며, CP949(MS949, x-windows-949)는 확장 완성형의 인코딩 방식이다. 그러므로 EUC-KR은 2,350자의 한글, CP949는 11,172자의 한글을 표현할 수 있다. 그러나 Java에서는 CP949와 MS949를 다르게 취급한다. CP949는 IBM에서 처음 지정한 코드 페이지(sun.nio.cs.ext.IBM949)가 기준이고 Microsoft가 제정한 확장 완성형은 MS949(sun.nio.cs.ext.MS949)를 기준이다. 그러므로 Java에서는 CP949와 EUC-KR이 사실상 같으며, 확장 완성형을 사용하기 위해서는 MS949로 지정해야 한다.
###유니코드 인코딩방식 
유니코드의 인코딩 방식으로는 코드 포인트를 코드화한 UCS-2와 UCS-4, 변환 인코딩 형식인 UTF-7, UTF-8, UTF-16, UTF-32 인코딩 등이 있다. 이 중 ASCII와 호환이 가능하면서 유니코드를 표현할 수 있는 UTF-8 인코딩이 가장 많이 사용된다. UTF-8은 코드 포인트 범위에 따라 다음 표에서 보는 바와 같이 인코딩 방식이 다르다.