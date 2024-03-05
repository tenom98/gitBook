# HTTP를 이해해보자

* ### HTTP(Hypertext Transfer Protocol)란<br>
  >HTML과 같은 하이퍼미디어 문서를 전송하기 위한 애플리케이션 계층 프로토콜
1. 프로토콜이란 규칙, 직합, 약속
2. 네트워크 프로토콜
   1. 물리 계층 (완전히 physical한 계층)
   2. 데이터 링크 계층 (하드웨어를 추상화, 각 기기를 구분 / MAC Address)
   3. 네트워크  계층 (IP Address - 원격에서 알수있는 내 접속정보)
   4. 전송 계층 (프로그램들 간 연결을 하기 위해 Port Number 사용)
      1. TCP 
      2. UDP 
   5. 응용계층 (web 브라우저 같은 것들)<br>
      https tls같은 보안 계층이 먼저 사용 가능함
* #### HTTP와 HTTPS의 차이(TLS)
>http는 브라우저나 서버간 정보를 교환할때 사용하는 프로토콜의 명칭<br>
https는 SSL/TLS로 암호화된 데이터 교환이 이루어진 경우에 사용

* #### 클라이언트와 서버간 통신<br>
  서비스/리소스 -> URL(<- 리소스를 특정하기 위해서 사용)<br>
  클라이언트 -> 요청을 한다<br>
  서버 -> (처리) -> 응답을 한다<br>

* ### Stateless(무상태)
> 무상태 = 연결 상태가 지속적이지 않다 <br>
특징) 각각의 요청이 독립적이다.<br> 
-> 항상 클라이언트가 자신을 특정해야한다.<br>
>

이때의 수단으로,<br> 
1. 요청과 응답을 통해 주고받는 쿠키.
2. 데이터는 서버에서 관리하고 쿠키 등으로 KEY를 관리하는 세션
3. 웹 브라우저의 기능( LocalStorage 등)<br>

가 있다.

* ### HTTP Cookie와 HTTP Session<br>
  요청과 응답을 통해 계속 주고 받는 쿠키<br>
  세션 자체는 서버에서 관리하는 데이터 처리를 위한 것<br>
(이때, 세션에 대한 key도 쿠키 혹은 url에 직접 삽입했었음

* ### HTTP 메시지 구조<br>
기본적으로는 사람이 읽을 수 있는 형태(암호화나 performance를 위해 Binary 사용하기도함)


* ### HTTP 요청(Request)와 응답(Response)<br>
둘의 구조는 동일함.<br>
startLine(요청과 응답의 형태는 다름) / Headers(속성(Attribute)이 여러개) / 빈줄 / Body(없어도됨.)<br>
- multipart/form-data
    : 대개는 하나의 데이터를 전송하나, 파일 업로드를 위해 쓰이는 것이 있다. 바디를 구분해서 여러개를 보낼때 사용

* ### HTTP 요청 메서드(HTTP request methods)
요청이란, 리소르를 통해 무엇을 하기 원하는지.<br>
(Create Read Update Delete)
1. Get -> Read 브라우저에서 url를 입력하여 요청하는 것.(웹서비스라면 해당 url을 사용하는 페이지로 이동하는 것이 예가 될수 있음)<br>
2. Head -> get with out body(존재하지 않는 ?)<br>
3. Post -> Submit (멱등성X)<br>
   - 멱등성 : 같은 것을 지속적으로 요청한다면, 항상 같은 것을 돌려준다.<br>
4. Put -> Update(+create) -> OverWrite(전부 뒤엎기)<br>
5. Patch -> Update -> Partial update (멱등성X)<br>
6. Delete -> delete<br>
7. Options -> 기능들이 지원가능한지 확인하는 용도로 사용 가능<br>

* ### HTTP 응답 상태 코드(HTTP response status code) - 요청에 대해 상태코드를 보내줌
  - 1xx → 정보 ⇒ 우리가 직접 쓰는 일은 드믐.
  - 2xx → 성공 ⇒ 200 OK, 201 Created, 204 No Content
  - 3xx → 리다이렉션 ⇒ 304 Not Modified가 특수한 형태로 자주 보임.(redirection에 있음)
    - 리다이렉션 : 다른 페이지로 옮겨주는 것
  - 4xx → 클라이언트 쪽 문제 ⇒ 404 Not Found
  - 5xx → 서버 쪽 문제 ⇒ 500 Internal Server Error



