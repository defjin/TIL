문자열을 표시하기 위해서 비트로(숫자) 매핑함. -> 지역마다 다른 방식 사용 -> 미국에서 초기에 지역간의 문자 통일을 위해서 ASCII 시작..(American Standard Code for Information Interchange) 7bit encoding 33개의 제어문자, 95개의 출력문자

8bit를 사용해서 확장아스키코드를 사용. 인터넷이 발달하면서 각 국가의 언어를 처리하기 위한 표준이 유니코드

한글의 경우 조합형과 완성형이 있음. 각 초-중-종성에 매핑. -> 프로그래밍하기에 어려움. 완성형의 경우에는 한 번에  완성글자 하나를 매핑함.

utf-8 이 가장 범용적임. 그 중에 1바이트 앞에는 ACSII가 들어있음. 가변길이 인코딩 방식.

대부분의 언어들이 utf-16 + (아주 간혹 utf-32) 일반적으로 os 에서 16, 웹에서 8

### big endian ,little endian

큰 단위 값을 앞에 저장 big,  작은 단위를 앞에 저장이 little -> 하드웨어를 다룰 때는 훨씬 중요함.

c 스타일의 문자열에서는 00000000 -> `\0` 을 만나면 문자열을 끝내도록 한다.

java 는 string 클래스에서 메모리를 컨트롤 할 수 있는 형태를 취한다.



pro레벨 테스트에서는 기본적인 연산을 모두 구현해야한다.



### 문자열 패턴 매칭

- 브루트포스! 본문 문자열을 전부 순회하면서 패턴 내의 문자들을 일일이 비교
-  KMP 알고리즘 : 패턴의 내부에서 같은 형태가 있는지를 찾음
- 보이어 무어 알고리즘 :  많은 프로그램이 이걸로 구현되어 있음



### 문자열 암호화

- 시저 암호
- 문자 변환표를 이용한 매핑
- bit 열의 암호화 - 배타적 논리합 사용(xor 두 번 사용하면 원래의 값이 나옴)



### 문자열 압축

- run-length encoding ; bmp에 사용됨. 같은 값이 몇 번 사용되는지를 알려줌
- 가로 압축과 세로 압축이 압축률이 틀림
- gif 는 다른 방식을 사용
- 허프만 코딩 알고리즘