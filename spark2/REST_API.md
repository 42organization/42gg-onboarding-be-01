# REST API란 무엇인가?

## REST(Representational State Transfer)란?

- 자원을 이름으로 구분하여 해당 자원의 상태를 주고받는 모든 것을 의미

### **즉, REST란**

1. HTTP URI(Uniform Resource Identifier)를 통해 자원(Resource)을 명시하고,
2. HTTP Method(POST, GET, PUT, DELETE, PATCH 등)를 통해
3. 해당 자원(URI)에 대한 CRUD Operation을 적용하는 것을 의미합니다.

`CRUD`란?

- 대부분의 컴퓨터 소프트웨어가 가지는 기본적인 데이터 처리 기능인 Create(생성), Read(읽기), Update(갱신), Delete(삭제)를 묶어서 일컫는 말

<aside>
💡 Create : 데이터 생성(POST)
Read : 데이터 조회(GET)
Update : 데이터 수정(PUT, PATCH)
Delete : 데이터 삭제(DELETE)

</aside>

### REST 구성 요소

1. **자원**(Resource) : HTTP URI
    - 모든 자원에 고유한 ID가 존재하고, 이 자원은 Server에 존재한다.
    - 자원을 구별하는 ID는 ‘/groups/:group_id’와 같은 HTTP URI 다.
    - Client는 URI를 이용해서 자원을 지정하고 해당 자원의 상태(정보)에 대한 조작을 Server에 요청한다.
2. 자원에 대한 **행위**(Verb) : HTTP Method
3. 자원에 대한 행위의 **표현**(Representations) : HTTP Message Pay Load
    - Client가 자원의 상태(정보)에 대한 조작을 요청하면 **Server는 이에 적절한 응답(Representation)을 보낸다.**
    - REST에서 하나의 자원은 JSON, XML, TEXT, RSS 등 여러 형태의 Representation으로 나타내어 질 수 있다.
    - **JSON** 혹은 **XML**를 통해 데이터를 주고 받는 것이 일반적이다.

### REST의 특징

1. **Server-Client(서버-클라이언트 구조)**
    - 자원이 있는 쪽이 Server, 자원을 요청하는 쪽이 Client
2. **Stateless(무상태)**
    - Client의 context를 Server에 저장하지 않는다.
        - 즉, 세션과 쿠키와 같은 context 정보를 신경쓰지 않아도 되므로 구현이 단순해진다.
    - Server는 각각의 요청을 완전히 별개의 것으로 인식하고 처리한다.
        - 각 API 서버는 Client의 요청만을 단순 처리한다.
3. **Cacheable(캐시 처리 가능)**
    - 웹 표준 **HTTP 프로토콜을 그대로 사용**하므로 웹에서 사용하는 **기존의 인프라를 그대로 활용**할 수 있다.
        - 즉, HTTP가 가진 가장 강력한 특징 중 하나인 캐싱 기능을 적용할 수 있다.
    - 대량의 요청을 효율적으로 처리하기 위해 캐시가 요구된다.
    - 캐시 사용을 통해 **응답시간이 빨라지고,** REST Server 트랜잭션이 발생하지 않기 때문에 **전체 응답시간, 성능, 서버의 자원 이용률을 향상**시킬 수 있다.
4. **Layered System(계층화)**
    - Client는 REST API Server만 호출한다.
    - REST Server는 **다중 계층**으로 구성될 수 있다.
    API Server는 순수 비즈니스 로직을 수행하고 그 앞단에 보안, 로드밸런싱, 암호화, 사용자 인증 등을 추가하여 구조상의 **유연성**을 줄 수 있다.
    또한 로드밸런싱, 공유 캐시 등을 통해 **확장성**과 **보안성**을 향상시킬 수 있다.
5. **Uniform Interface(인터페이스 일관성)**
    - URI로 지정한 Resource에 대한 조작을 통일되고 한정적인 인터페이스로 수행한다.
    - HTTP 표준 프로토콜에 따르는 모든 플랫폼에서 사용이 가능하다.
        - 특정 언어나 기술에 종속되지 않는다.

### REST의 장단점

- 장점
    - **HTTP 프로토콜의 인프라를 그대로 사용하므로** REST API 사용을 위한 **별도의 인프라를 구출할 필요가 없다.**
    - HTTP 프로토콜의 표준을 최대한 활용하여 여러 추가적인 장점을 함께 가져갈 수 있게 해준다.
    - HTTP 표준 프로토콜에 따르는 모든 플랫폼에서 사용이 가능하다.
    - REST API 메시지가 **의도하는 바를 명확하게 나타내므로 의도하는 바를 쉽게 파악할 수 있다.**
- 단점
    - **표준이 자체가 존재하지 않아** 정의가 필요하다.
    - HTTP Method 형태가 제한적이다.
        - **사용할 수 있는 메소드가 4가지 밖에 없다**.
    - 구형 브라우저에서 호환이 되지 않아 지원해주지 못하는 동작이 많다.(익스폴로어)

## REST API란?

### API(Application Programming Interface)란?

- 데이터와 기능의 집합을 제공하여 **컴퓨터 프로그램간 상호작용을 촉진**하며, **서로 정보를 교환가능 하도록 하는 것**

### REST API의 정의

- REST의 원리를 따르는 API
- 최근 **OpenAPI**(누구나 사용할 수 있도록 공개된 API: 구글 맵, 공공 데이터 등), **마이크로 서비스**(하나의 큰 애플리케이션을 여러 개의 작은 애플리케이션으로 쪼개어 변경과 조합이 가능하도록 만든 아키텍처) **등을 제공하는 업체 대부분은 REST API를 제공**한다.

### **REST API 설계 예시**

1. URI는 동사보다는 명사를, 대문자보다는 소문자를 사용하여야 한다.

> Bad Example http://khj93.com/Running/Good Example  http://khj93.com/run/
> 

2. 마지막에 슬래시 (/)를 포함하지 않는다.

> Bad Example http://khj93.com/test/  Good Example  http://khj93.com/test
> 

3. 언더바 대신 하이폰을 사용한다.

> Bad Example http://khj93.com/test_blogGood Example  http://khj93.com/test-blog
> 

4. 파일확장자는 URI에 포함하지 않는다.

> Bad Example http://khj93.com/photo.jpg  Good Example  http://khj93.com/photo
> 

5. 행위를 포함하지 않는다.

> Bad Example http://khj93.com/delete-post/1  Good Example  http://khj93.com/post/1
> 

### RESTful이란?

- REST의 원리를 따르는 시스템을 의미.
- 하지만 REST를 사용했다 하여 모두가 RESTful 한 것은 아니며,  REST API의 설계 규칙을 올바르게 지킨 시스템을 RESTful하다 말할 수 있다.