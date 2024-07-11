### [ARP 프로토콜](https://youtu.be/LDsp-Xb168E?list=PL0d8NnikouEWcF1jJueLdjRIC4HsUlULi)

-

### ARP 프로토콜의 통신 과정

#### ARP 프로토콜

- ARP가 하는 일: 같은 네트워크 대역에서 통신을 하기 위해 필요한 MAC주소를 IP주소를 이용해 알아오는 프로토콜

- 구조(28byte)

  - Hardware Type (2 byte): 2계층에서 사용하는 프로토콜의 타입 (0001:이더넷)
  - Protocol Type (2 byte): 3계층에서 사용하는 프로토콜의 타입 (0800: IPv4 프로토콜)
  - Hardware Add. length (1 byte): MAC 주소의 크기 (06)
  - Protocol Add. length (1 byte): IPv4 주소의 크기 (04)
  - Opcode (2 byte): 오퍼레이션 코드 (MAC주소를 요청 중인지? 001 : 002)
  - source hardware Add.(6 byte): 출발지 MAC주소
  - source protocol Add.(4 byte): 출발지 IPv4 주소
  - destination hardware Add. (6 byte): 목적지 MAC주소
  - destination protocol Add. (4 byte): 목적지 IPv4주소

### ARP 테이블

- 나와 통신했던 컴퓨터들의 주소
