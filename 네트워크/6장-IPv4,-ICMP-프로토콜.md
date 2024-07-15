### [IPv4 프로토콜](https://youtu.be/_i8O_o2ozlE?list=PL0d8NnikouEWcF1jJueLdjRIC4HsUlULi)

#### IPv4가 하는 일

- 원거리 네트워크 상에서 데이터를 교환하기 위한 프로토콜 (다른 네트워크의 특정 대상을 찾는 프로토콜)
- 데이터가 정확하게 전달될 것을 보장하지 않는다.
  - 중복된 패킷을 전달하거나 패킷의 순서를 잘못 전달할 가능성도 있다.
  - 데이터의 정확하고 순차적인 전달은 상위 프로토콜인 <b>TCP</b>에서 담당

#### IPv4의 구조

- 20byte, 옵션이 붙을 시 하나당 4byte씩 추가
- version (4 bit): IP 프로토콜의 버전, 무조건 4가 온다고 보면 됨 (v4, v6)
- IHL (Header Length, 4bit): (헤더 길이) / 4 를 2진수 4개로 표현 (20 ~ 60자)
- TOS (Type Of Service, 1 byte): 지금은 안 씀, 0
- Total Length (payload 까지 포함된 전체 길이, 2 byte)

- 데이터 최대 전송 길이에 맞추어 쪼개진 값 인식

  - Identification (2 byte): 식별자, ID가 같은 데이터끼리 합침
  - IP Flags (0.8 byte)
  - Fragmant Offset (1.2 byte): 조합 순서

- TTL (Time To Live, 1 byte): 패킷이 살아있을 수 있는 시간
  - 패킷이 계속 살아있으면 DOS공격같이 된다..
  - 라우터 등 다른 장비를 통과할 때마다 시간이 1씩 줄어들다가 0이 되면 전달을 멈춤
- Protocol (1 byte): 상위 프로토콜이 뭔 지 알려줌 (ICMP: 3계층, 01 / TCP: 4계층, 06 / UDP: 4계층, 17), 이더넷타입이랑 동일한 역할
- Header Checksum (2 byte): 헤더에 오류가 있는 지 없는 지 확인하는 역할
- source Add. (4 byte)
- destination Add. (4 byte)

### [ICMP 프로토콜](https://youtu.be/JaBCIUsFE74?list=PL0d8NnikouEWcF1jJueLdjRIC4HsUlULi)

#### ICMP 프로토콜이 하는일

- 네트워크 컴퓨터 위에서 돌아가는 운영체제에서 오류 메세지를 전송받는 데 사용되는 프로토콜

#### ICMP 프로토콜의 구조

- type (1 byte): 대분류
  - 0, 8 (응답, 요청)
  - 3, 11 (destination unreachable: 가는 경로상의 문제, time exceed: 상대방 문제)
  - 5 (ICMP Redirect): 원격지에서 routing table을 수정할 수 있음
- code (1 byte): 소분류
- checksum (2 byte): 오류 확인

### [라우팅 테이블](https://youtu.be/CjnKNIyREHA?list=PL0d8NnikouEWcF1jJueLdjRIC4HsUlULi)

- 내가 보낸 패킷의 목적지가 설정되어 있는 지도 역할을 함

### [IPv4 조각화 이론](https://youtu.be/_AONcID7Sc8?list=PL0d8NnikouEWcF1jJueLdjRIC4HsUlULi)

#### 조각화란?

- 큰 IP 패킷들이 적은 MTU (Maximum Transmission Unit, 보통 1500)를 갖는 링크를 통하여 전송되려면 <u>여러 개의 작은 패킷으로 쪼개어/조각화 되어</u> 전송되어야 한다.
