### [NAT란?](https://youtu.be/Qle5cfCcuEY?list=PL0d8NnikouEWcF1jJueLdjRIC4HsUlULi)

#### NAT (Network Address Translation)

- IP 패킷의 TCP/UDP 포트 숫자와 소스 및 목적지의 IP주소 등을 <u>재기록</u>하면서 라우터를 통해 네트워크 트래픽을 주고 받는 기술
- 패킷에 변화가 생기기 때문에 IP나 TCP/UDP의 체크섬(checksum)도 다시 계산되어 재기록해야한다.
- 주로 <u>사설 IP를 공인 IP로 변환</u>하는 데에 사용한다. (여기에만 쓰는 건 아님)

### 포트 포워딩

- 특정 IP주소와 포트 번호의 통신 요청을 특정 다른 IP와 포트 번호로 넘겨주는 NAT 응용 기술
  - 서버가 사설 네트워크 대역에 있을 때 그 네트워크 대역의 라우터 같은 데에서 제공해주는 기능
  - 사설 IP에서 공인 IP의 특정 포트로 요청 전송 -> 공유기에서 해당 요청을 특정 IP의 특정 포트로 전송
