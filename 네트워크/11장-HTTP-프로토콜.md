### [HTTP 프로토콜](https://youtu.be/TwsQX1AnWJU?list=PL0d8NnikouEWcF1jJueLdjRIC4HsUlULi)

#### 웹을 만드는 기술들

- HTTP (HTTPS -> SSL/TLS)
- 클라이언트 사이드에서 동작하는 코드 (웹 표준)

  - HTML: 웹 페이지를 채울 내용
  - JavaScript: 웹 페이지에 들어갈 기능
  - CSS(Cascade Style Sheet): 웹 페이지를꾸밀 디자인

- 서버에서 동작하는 코드

  - ASP/ASP.NET
  - JSP
  - PHP

- DB

#### HTTP (HyperText Transfer Protocol)

- HTTP의 특징

  - www에서 쓰이는 핵심 프로토콜로 오늘날 거의 모은 웹 app에서 사용되고 있다.
  - Request / Response 동작에 기반하여 서비스 제공

  - HTTP 1.0 (구버전, 현재 1.1 사용)
    - 문서를 전송받은 뒤 연결을 끊고 다시 연결하여 데이터를 전송한다.
    - 단순 동작이 반복되어 통신 부하 발생

### [HTTP 요청 프로토콜](https://youtu.be/rxaBwwI_JnI?list=PL0d8NnikouEWcF1jJueLdjRIC4HsUlULi)

#### HTTP <u>요청</u> 프로토콜

- 구조

  - Request Line: 리퀘스트 메서드 등 정보
  - Headers: 옵션
  - 공백 (1줄)
  - Body

- 메소드

  | 메소드 종류 | 설명                                                        |
  | ----------- | ----------------------------------------------------------- |
  | <b>GET</b>  | Client가 Server로부터 문서를 읽어오려 할 때 사용            |
  | HEAD        | Client가 문서가 아닌 문서에 대한 특정 정보를 원할 경우 사용 |
  | <b>POST</b> | Client가 Server에게 어떤 정보를 전송                        |
  | PUT         | Client가 Sever에 특정 자원을 업로드                         |
  | PATCH       | PUT과 비슷, 기존 파일에서 변경사항만을 포함                 |
  | COPY        | 파일을 다른 위치로 복사                                     |
  | MOVE        | 파일을 다른 위치로 이동                                     |
  | DELETE      | Sever에서 문서를 제거                                       |
  | LINK        | 문서에서 다른 위치로의 링크를 생성                          |
  | UNLINK      | Link Method에 의해 생성된 링크를 삭제                       |
  | OPTION      | Client가 Server에게 사용 가능한 옵션을 질의                 |

### [URL, URI란?](https://youtu.be/2ikhZ_fNP5Y?list=PL0d8NnikouEWcF1jJueLdjRIC4HsUlULi)

#### URI (Uniform Resource Identifier)

- 인터넷 상에서 특정 자원을 나타내는 유일한 주소
- scheme ://host :port /path ?query
- ex
  - ftp ://IP주소 :포트 /파일이름
  - http ://IP주소 :포트 /폴더이름/파일이름
  - 도메인 => DNS => IP주소 (포트는 브라우저에서 자동으로 변환해줌)

#### URL (Uniform Resource Locater)

- URI의 일종
- 네트워크상 리소스의 위치를 나타내기 위한 규약

### [HTTP 응답 프로토콜](https://youtu.be/kuucNF4Zvbs?list=PL0d8NnikouEWcF1jJueLdjRIC4HsUlULi)

#### HTTP <u>응답</u> 프로토콜

- 구조

  - Status Line: 응답 스테이터스 정보 (status code같은 거)
  - Headers: 옵션
  - 공백 (1줄)
  - Body

- 상태 코드

| 상태 코드 종류 | 설명                                            | 예시                                        |
| :------------: | ----------------------------------------------- | ------------------------------------------- |
|   100 ~ 199    | 단순한 정보                                     |                                             |
|   200 ~ 299    | 성공                                            | 200 OK                                      |
|   300 ~ 399    | Client의 요청이 수행되지 않아 다른 URL로 재지정 |                                             |
|   400 ~ 499    | Client에서 요청을 잘못 보냄                     | 401 Unauthorized 403 Forbidden 404 NotFound |
|   500 ~ 599    | Sever 오류                                      | 500 Internal Sever Error                    |

### [HTTP 헤더 포맷](https://youtu.be/mQTGmxendk8?list=PL0d8NnikouEWcF1jJueLdjRIC4HsUlULi)

- 일반 헤더

  |   헤더 종류    | 설명                               |
  | :------------: | ---------------------------------- |
  | Content-Length | 메세지 바디 길이                   |
  |  Content-Type  | 메세지 바디에 들어있는 컨텐츠 종류 |

- 요청 헤더

  | 헤더 종류  | 설명                                                        |
  | :--------: | ----------------------------------------------------------- |
  |   Cookie   | 서버로부터 받은 쿠키를 다시 서버로 보내는 역할              |
  |    Host    | 요청한 URL에 나타난 호스트명을 상세히 표시                  |
  | User-Agent | Client Program에 대한 식별 기능 정보 제공 (OS, 브라우저 등) |

- 응답 헤더

  | 헤더 종류  | 설명                                                  |
  | :--------: | ----------------------------------------------------- |
  |   Server   | 사용하고 있는 웹 서버의 소프트웨어에 대한 정보를 포함 |
  | Set-Cookie | 쿠키를 생성하고 브라우저에 보낼 때 사용               |
