# HTTP & REST API

# HTTP

[HTTP 헤더 - HTTP | MDN](https://developer.mozilla.org/ko/docs/Web/HTTP/Headers)

- HyperText Transfer Protocol
- W3 상에서 정보를 주고받을 수 있는 프로토콜
- 클라이언트 ↔ 서버 사이에 이루어지는 Request/Response 프로토콜
- HTML 문서와 같은 리소스들을 가져올 수 있도록 하는 프로토콜
- 주로 TCP 사용하고, HTTP/3 부터는 UDP를 사용하며, 80번 포트 사용
- 요청하기 위해 연결하면 다음 응답 받을때 까지 대기
- 무상태 프로토콜 (요청 간 어떠한 데이터, 상태도 유지하지 않음)

### Method

- GET
    - 쿼리 파라미터, 쿼리 스트링
- POST
    - 파일 데이터 전송 과정
- PUT
- PATCH
- DELETE
- HEAD
- OPTIONS
- CONNECT
- TRACE

### Status Code

### Header

- 부가적인 정보 전송
- 대소문자를 구분하지 않고 이름과 콜론 다음에 오는 값으로 이루어짐
- context에 따라 그룹핑
    - General Header
    - Entity Header
    - Request Header
    - Response Header
- 프록시 처리 방법에 따라 그룹핑
    - 종단간 헤더
        - 최종 수신자에게 전송되어야 함
        - 요청에 대해서는 서버, 응답에 대해서는 클라이언트
        - 중간 프록시는 반드시 종단 간 헤더를 수정되지 않은 상태로 재전송해야 하며 캐시는 이를 반드시 저장해야 함
    - 홉간 헤더
        - `Connection`, `Keep-Alive`, `Proxy-Authenticate`, `Proxy-Authorization`, `Trailer`, `Transfer-Encoding`, `Upgrade`,

# REST API

- **Representational State Transfer**
- **자원을 이름으로 구분하여 해당 자원의 상태를 주고 받는 모든 것**
- HTTP URI(Uniform Resource Identifier)를 통해 자원(Resource)를 명시하고, HTTP Method를 통해 해당 자원에 대한 CRUD Operation 적용하는 것

### REST 구성 요소

- Resource(자원) → URI
    - 모든 자원에 고유한 ID가 존재하고, 이 자원은 서버에 존재함
- Verb (행위) → HTTP Method
- Representation of Resource (표현) → JSON, XML, TEXT, RSS 등

### API

- **Application Programming Interface**
- 다른 소프트웨어 시스템과 통신하기 위해 따라야 하는 규칙 정의
- 클라이언트와 웹 리소스 사이의 게이트웨이

### REST API

- REST 기반으로 서비스 API 구현하는 것
- 설계 규칙
    - URI는 정보의 자원을 표현 (행위는 HTTP Method로)
    - `/`는 계층 관계를 나타냄
    - `-`는 URI 가독성 높임
    - `_`는 사용하지 않는다
    - URI 경로에는 소문자가 적합
    - 파일 확장자는 URI에 포함하지 않음

### RESTful

- REST 아키텍어를 구현하는 웹 서비스를 나타내기 위해 사용되는 용어
- REST API를 제공하는 웹 서비스 → ‘RESTful’ 함
- REST 원리를 따르는 시스템

## POST vs PUT

멱등성 보장하지 않음