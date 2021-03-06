### 1. 연결 리스트의 개념에 대해 설명해보세요

연결 리스트란 메모리의 동적 할당을 기반으로 구현된 리스트를 뜻합니다.

배열에 비해 추가 / 삭제가 용이한 것이 장점입니다. 하지만 특정 데이터를 찾기 위해서는 순차 탐색을 하므로 탐색 속도가 느린 단점이 있습니다. 또한 동적 할당을 기반으로 한 리스트이기 때문에 크기를 미리 지정할 필요가 없습니다.

참고: [https://m.blog.naver.com/pgh7092/221093740186]



### 2. DNS에 대해 설명해주세요

원래의 IP주소를 기억하기 쉬운 도메인으로 바꾸거나 도메인을 다시 IP주소로 바꾸어주는 데이터베이스 시스템

연결되어있는 IP주소와 도메인이 저장된 곳이 DNS

각 도메인들마다 DNS와 연결해주는 서버 역할을 하는 DNS 서버, 다른 말로 네임서버가 있다.

**작동 방식**

1. 주소.com을 입력

2. 주소.com을 가지고 있는 네임 서버에 접속

3. IP 주소를 확인

4. IP 주소를 전달

5. IP 주소를 가진 서버로 접속

6. 연결된 브라우저 실행

참고: [https://nack1400.tistory.com/21]



### 3. 프로세스와 스레드에 대해 설명해보세요

#### 프로세스

* 컴퓨터에서 연속적으로 실행되고 있는 컴퓨터 프로그램
* 메모리에 올라와 실행되고 있는 프로그램의 인스턴스
* 운영체제로부터 시스템 자원을 할당받는 작업의 단위
* 동적인 개념으로는 실행된 프로그램을 의미

#### 쓰레드

* 프로세스 내에서 실행되는 여러 흐름의 단위
* 프로세스의 특정한 수행 경로
* 프로세스가 할당 받은 자원을 이용하는 실행의 단위

참고: [https://juyoung-1008.tistory.com/47]



### 4. 브라우저는 어떻게 동작하나요?

1. DOM, CSSOM생성: 가장 첫번째 단계로 서버로부터 받은 HTML, CSS를 다운받는다 → 단순한 텍스트인 HTML, CSS파일을 Object Model로 만든다. HTML은 DOM으로, CSS는 CSSOM으로 만들어진다. (html이 여기서 파싱된다)
      DOM Tree와 CSSOM Tree가 만들어진다
2. Render Tree생성: DOM Tree와 CSSOM Tree가 만들어졌으면 그 다음으로는 이 둘을 이용하여 Render Tree를 생성한다. 렌더트리에는 스타일 정보가 설정되어있고, 실제 화면에 표현되는 노드들로 구성된다. 
3. Layout 단계: 브라우저의 뷰포트(Viewport) 내에서 각 노드들의 정확한 위치와 크기를 계산한다. 생성된 Render Tree 노드들이 가지고 있는 스타일과 속성에 따라서 브라우저 화면의 어느위치에 어느크기로 출력될지 계산하는 단계이다. 레이아웃 단계에서 %, vh, vw와 같이 상대적인 위치, 크기 속성은 실제 화면에 그려지는 픽셀 단위로 변환된다. 
4. Paint: Layout 계산이 완료되면 이제 요소들을 실제 화면을 그리게된다. 처리해야하는 스타일이 복잡할수록 paint 단계에 소요되는 시간이 길다. (가령 그라데이션, 그림자 효과 > 단색 배경)

참고: [https://d2.naver.com/helloworld/59361]

어렵습니다... 한 번 읽어 보세요



### 5. 주소창에 naver.com을 입력하면 어떤 일이 발생하는가?

1. 사용자가 입력한 url 주소 중에서 도메인 네임을 DNS 서버에서 검색한다. 
2. DNS 서버에서 해당 도메인 네임에 해당하는 IP주소를 찾아 사용자가 입력한 URL 정보와 함께 전달함
3. 웹 페이지 URL + IP 주소는 HTTP 프로토콜을 사용하여 HTTP 요청 메세지를 생성한다
4.  HTTP 요청 메세지는 TCP 프로토콜을 사용하여 인터넷을 거쳐 해당 IP 주소의 컴퓨터로 전송된다
5. 이렇게 도착한 HTTP 요청 메세지는 HTTP 프로토콜을 사용하여 웹 페이지 URL 정보로 변환된다.
6. 웹 서버는 도착한 웹 페이지 URL 정보에 해당하는 데이터를 검색한다.
7. 검색된 웹 페이지 데이터는 또다시 HTTP 프로토콜을 사용하여 HTTP 응답 메세지를 생성한다 
8. 이렇게 생성된 HTTP 응답 메세지는 TCP 프로토콜을 사용하여 인터넷을 거쳐 원래 컴퓨터로 전달된다.
9. 도착한 HTTP 응답 메세지는 HTTP 프로토콜을 이용하여 웹 페이지 데이터로 변환되고, 웹 브라우저에 의해 출력되어 사용자가 볼 수 있게 된다. 

