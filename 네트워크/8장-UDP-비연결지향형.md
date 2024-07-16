### [UDP 프로토콜](https://youtu.be/3MkI3FBFzX8?list=PL0d8NnikouEWcF1jJueLdjRIC4HsUlULi)

#### UDP 프로토콜(사용자 데이터그램 프로토콜, User Datagram Protocol)

- UDP가 하는 일

  - 전송 방식이 단순해서 신뢰성이 낮고, 데이터 도착 순서가 바뀌거나 누락되는 경우도 있다.
  - 일반적으로 <b>오류의 검사와 수정이 필요 없는</b> 프로그램에서 수행할 것으로 가정한다.

- UDP 프로토콜의 구조

  - Source Port (2 byte): 출발지 포트번호
  - Destination Port (2 byte): 도착지 포트번호
  - Length (2 byte): 헤더+payload
  - Checksum (2 byte): 헤더 프로토콜의 오류 여부

- UDP 프로토콜을 사용하는 프로그램

  - DNS 서버: 도메인을 입력하면 IP주소를 알려주는 서버
  - tftp 서버: 파일 전송 프로그램
  - RIP 프로토콜: 라우팅 정보 공유
