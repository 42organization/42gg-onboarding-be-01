# REST API

# REST
### 정의
- REpresentational State Transfer 아키텍처

### Uniform Interface
- identification of resources
    - 인터페이스는 클라이언트 서버 상호작용에서 각 리소스를 유일하게 식별할 수 있어야 한다.
- Manipulation of resources through representations
    - 서버의 응답에서 리소스의 표현은 균일하여야 한다.
    - API 소비자는 이러한 표현을 통해 리소스를 조작할 수 있어야 한다.
- Self-descriptive messages
    - 각 리소스 표현은 메시지 처리 방법을 처리하기에 충분한 정보를 가지고 있어야 한다.
    - 클라이언트가 리소스를 조작하기 충분한 정보를 가지고 있어야 한다.
- Hypermedia as the engine of application state
    - 클라이언트는 애플리케이션의 초기 URI만 알고 있어야 한다.
    - 애플리케이션의 상태는 Hyperlink를 통해 전이되어야 한다.

### Client-Server
- 클라이언트와 서버는 각각 분리되어 있고, 독립적으로 확장할 수 있다.

### Statelessness
- 각 요청은 성공적으로 처리되기 위해 필요한 모든 정보를 포함해야 한다.
- 서버는 클라이언트의 상태를 저장하지 않는다.
- 이러한 이유로 클라이언트 앱은 세션 상태를 유지해야 한다.

### Cacheable
- 캐시 가능한 제약조건은 응답이 암시적 또는 명시적으로 캐시 가능하거나 캐시 불가능한 것으로 표시해야 한다.
- 캐시 가능한 경우 클라이언트는 응답을 재사용할 수 있다.

### Code on demand
- 필요에 따라, 서버는 실행 가능한 코드를 클라이언트에 전송할 수 있다. 
- 이것은 클라이언트의 기능을 일시적으로 확장할 수 있게 한다.

# REST API
### 정의
- REST 아키텍처 스타일을 따르는 API
- 목적은 URL을 통해 의도를 명확하게 전달하고, 리소스를 조작하는 것이다.

### 구현
- HTTP 요청을 통해 리소스 내에서 CRUD 작업을 수행하는 것으로 구현된다.
- 일반적으로 GET, POST, PUT, DELETE 메소드와 URL을 통해 리소스를 조작한다.

# RESTful?
### 정의
- REST 스타일을 준수하도록 구현된 것

### RESTful API
- REST API를 준수하는 것
