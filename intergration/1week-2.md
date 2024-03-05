* ### TCP/IP 통신<br>
>Internet Protocol Suite : 인터넷에서 컴퓨터들이 서로 정보를 주고받는 데 쓰이는 통신 프로토콜<br>
  인터넷 프로토콜 슈트 중 TCP와 IP가 가장 많이 쓰이기 때문에 TCP/IP 프로토콜 슈트 라고 부름<br>

* ### 전송계층의 TCP UDP<br>
  - tcp : 연결이 필요함 (전달 및 순서 보장 ex. 전화 - 받지않으면 성립이 안됨)<br>
  - udp : 연결하지 않고 데이터를 보냄(전달 및 순서를 보장하지 않음 ex. 편지 - 받지 않아도 보내는 것엔 지장이 없으며, 상대 수신여부에 대한 파악이 어려움)<br>
> TCP 와 UDP 프로토콜을 사용할때에는 Socket 통신으로 한다.
* ### Socket과 Socket API 구분 <br>
  - socket : 네트워크 소켓 - 프로세스 간 통신의 EndPoint / 파일과 유사하게 다룰 수 있다 (열고 닫고 편집하고, UNIX에선 파일디스크립터의 일종)<br>
JAVA에서는 stream(sysout sysin 처럼 매우 기본적인 키보드 입력, 화면 춝력, 파일 입출력 등의 IO)을 이용할 수 있다.<br>
  - socket API : Socket을 위한 API<br>

* ### tcp 통신순서<br>
 1. 서버는 접속요청을 받기 위한 소켓을 연다 (Listen)<br>
2. 클라이언트는 소켓을 만들고, 서버에 접속을 요청한다 (Connect)<br>
3. 서버는 접속 요청을 받아서 클라이언트와 통신할 소켓을 따로 만든다 (Accept)<br>
4. 소켓을 통해 서로 데이터를 주고 받는다 (Send & Receive 반복)<br>
5. 통신을 마치면 소켓을 닫는다 (Close -> 해당 조치는 요청자와 서버 둘다 할 수 있으며 Recevie로 인지함)<br>

* ### URI와 URL
  - URI : 식별자를 가지는 자원의 실제 위치 Uniform Resource Identifier
  - URL : 자원의 실제 위치 Uniform Resource Locator

* ### 호스트(host)
  - IP 주소 : 고유한 숫자로 된 주소<br>
  - Domain name : IP주소보다 기억하기 쉬운 문자열로 구성된 주소명<br>
  - DNS : 도메인 네임과 IP를 연결시켜주는 시스템  Domain Name System<br>
* ### 포트(port)<br>
  * 포트 번호가 할당된 _소켓_ 은 TCP/IP 상위의 응용 프로그램을 구분하기 위한 번호<br>

* ### path(경로)<br>
  * 절대경로 <br>
