### [TCP 프로토콜](https://youtu.be/cOK_f9_k_O0?list=PL0d8NnikouEWcF1jJueLdjRIC4HsUlULi)

#### TCP 프로토콜 (전송 제어 프로토콜, Transmission Control Protocol)

- TCP 프로토콜이 하는 일

  - 데이터를 <u>안정적으로, 순서대로, 에러 없이</u> 교환할 수 있게 하는 프로토콜
  - UDP보다 안전하지만 느리다

- TCP 프로토콜의 구조 (20 ~ 60 byte)

  - Source Port (2 byte): 출발지 포트번호
  - Dest. Port (2 byte): 도착지 포트번호
  - Sequance No. (4 byte): 내 번호
  - Acknowledgement No. (4 byte): 상대 번호+1
  - Offset (1 byte): 헤더의 길이를 4로 나눈 것
  - Resolved (1 byte): 예약된 필드 (사용하지 않는 필드)
  - TCP Flags (2 byte): TCP의 기능을 표시
  - Window (2 byte): 내 사용 공간이 얼마나 남아있는 지 상대방에게 알려주는 역할 (내 TCP Buffer 공간)
  - Checksum (2 byte): 헤더 프로토콜의 오류 여부
  - Urgent Pointer (2 byte): Urgent Flag의 위치값
  - TCP Options (4 byte ~)

- TCP 플래그
  - C E <b>U A P R S F</b>
  - U (Urgent Flag): 우선순위가 높은 데이터가 포함됨
  - A (Ack Flag): 승인을 해줄 때 사용하는 플래그
  - P (Push): 버퍼의 크기와 상관 없이 데이터를 밀어 넣는 플래그
  - R (Reset): 연결 초기화
  - S (Sync): 동기화 비트, 상대방과 연결을 시작할 때 사용하는 플래그
  - F (Fin): 종료 비트

### [TCP 3Way Handshake](https://youtu.be/Ah4-MWISel8?list=PL0d8NnikouEWcF1jJueLdjRIC4HsUlULi)

#### TCP를 이용한 통신과정

- 연결 수립 과정 (<b>3 Way Handshake</b>): TCP를 이용한 데이터 통신 시 프로세스끼리 연결하기 위해 가장 먼저 수행되는 과정

  - 클라이언트가 서버에게 요청 패킷을 전송
  - 서버가 클라이언트의 요청을 승인하는 패킷을 전송
  - 클라이언트는 이를 최종적으로 수락하는 패킷을 전송

- Sequence No. & Ack No. (동기화를 위한 번호)

  - Sequence No. 처음 생성 시 랜덤값 생성
  - Ack No.는 자기가 받은 Seq No. 에 1을 더한 것
  - 다음 Seq No.는 받은 Ack No.를 사용

- 세션 하이재킹: 연결 수립 후 클라이언트가 데이터를 보내야 하는데.. 해커가 그 값을 뽀려서 대신 세션에 참가하는 것

### [TCP를 이용한 데이터 전송 과정](https://youtu.be/0vBR666GZ5o?list=PL0d8NnikouEWcF1jJueLdjRIC4HsUlULi)

#### 데이터 송수신 과정

- 보낸 쪽에서 데이터를 또 보낼 Seq와 Ack No.를 그대로 사용
- 받는 쪽에서 Seq. 번호는 받은 Ack. 번호가 된다.
- 받는 쪽에서 Ack. 번호는 Seq. 번호 + 데이터의 크기가 된다.
