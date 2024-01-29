### REST API 란 무엇인가?

**REST(Representational State Transfer)**

- HTTP를 잘 사용하기 위한 아키텍처 스타일
- URI와 메소드를 사용해서 리소스와 행위를 표현
- `RESTful` : REST의 원칙을 지키면서 API의 의미를 파악하기 쉽게 한 것

**REST API**

- REST한 방식으로 설계된 API
- URL로 어떤 자원에 접근할지 표현, 메소드로 어떤 행위를 할 것인지 표현
- stateless 한 특징

**REST API의 장점**

- 보기에 편함 - URL만 보고 어떤 자원에 접근해서 어떤 행위를 하는지 알 수 있음
- 1개의 URI로 4개의 행위를 명시할 수 있어 효율적이고, 자원을 아낄 수 있음
- `stateless` 한 상태를 유지할 수 있음 - 다양한 모바일과 브라우저에서 통신할 수 있고, 클라이언트가 서버에 종속적이지 않아도 됨