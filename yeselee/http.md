## **HTTP METHOD**

**HTTP METHOD란**

- 클라이언트-서버 구조에서 request, response가 이루어지는 방식
- `서버가 수행할 동작을 지정` 하는 것

**사용 이유**

- 리소스와 동작을 분리하기 위함

**메소드의 종류**

- 크게 9가지가 있음
  - 주로 사용되는 메서드는 `GET, POST, PUT, PATCH, DELETE`
  - 기타 메서드:  `HEAD, OPTIONS, CONNECT, TRACE`

**GET**

- `리소스를 조회` 하는 메서드
- 데이터를 전달하려고 하는 경우 `쿼리 스트링`을 사용함 (바디 x)
- 형식
    ```html
    // 정적 데이터
    GET /index.html
    
    // 쿼리 스트링 이용하여 동적 데이터 전달
    GET /members?class=101&id=11
    ```

**POST**

- `전달한 리소스를 처리/생성 요청`하는 메서드
- 전달할 데이터를 바디에 담아 보냄
- 성공 시 `201(created)` 반환
- 형식
    ```html
    POST /members
    
    {
    "name": "ann",
    "age": "19"
    }
    ```

**PUT**

- `리소스를 수정` 하는 메서드
- 해당 리소스가 존재하면 덮어쓰고, 없으면 새로 생성함
- 부분 수정 불가능, 바꾸려는 전체 데이터를 보내야 함
- 형식
    ```html
    PUT /members/100

    {
    "name": "ann",
    "age": "12"  
    }
    ```

  아래와 같이 보내면 name 정보는 사라지고 age만 등록됨

    (기존 정보를 아래 정보로 완전히 대체하기 때문에)

    ```html
    PUT /members/100
    
    {
    "age": "12"  
    }
    ```

**PATCH**

- `리소스를 일부만 변경` 하는 메서드
- 형식
    ```html
    PATCH /members/100
    
    {
    "age": "12"  
    }
    ```
  
**DELETE**

- `리소스를 제거` 하는 메서드
- 성공 시
- 형식
    ```html
    DELETE /members/100
    ```

## **HTTP Status Code**

**HTTP Status Code란**

- 응답 메시지에서 `서버의 처리 결과`를 나타내기 위한 것
- 100~500번 대까지 상태 코드가 정의되어 있음

****1XX: Informational(정보 제공)****

- 요청을 받았으며 작업을 계속 진행하라

****2XX: Success(성공)****

- 요청을 성공적으로 처리함
- `200(OK)` : 요청을 성공적으로 처리함
- `201(Created)` : 요청이 처리되어 새로운 리소스가 생성됨
- `202(Accepted)` : 요청은 접수되었으나, 처리가 완료되지 않았음
- `204(No Content)` : 처리는 성공했으나, 클라이언트에게 돌려줄 컨텐츠가 없음. 주로 delete 요청에 사용

****3XX: Redirection(리다이렉션)****

- 완전한 처리를 위해서 추가 동작이 필요함
- `301(Moved Permanently)` : 요청한 리소스가 새로운 URI로 변경되었음
- `302(Found)` : 요청한 리소스의 URI가 일시적으로 변경되었음

****4XX: Client Error(클라이언트 에러)****

- 클라이언트의 요청에서 오류가 있음
- `400(Bad Request)` : 요청이 잘못됨. 잘못된 문법으로 서버가 이해할 수 없음
- `401(Unauthorized)` : 요청한 리소스에 대한 권한이 없음
- `403(Forbidden)` : 클라이언트가 리소스에 접근할 권리를 가지고 있지 않음
- `404(Not Found)` : 서버가 요청받은 리소스를 찾을 수 없음
- `405(Method Not Allowed)` : 서버가 해당 메서드를 지원하지 않음

****5XX: Server Error(서버 에러)****

- 클라이언트의 요청은 유효, 서버에서 처리를 실패함
- `500(Internal Server Error)` : 서버에서 에러가 발생함
- `501(Not Implemented)` : 서버가 해당 기능을 지원하지 않음. 아직 개발이 덜 됨
- `502(Bad Gateway)` : 서버가 다른 서버로부터 유효하지 않은 응답을 받은 경우
- `503 (Service Unavailable)` : 일시적으로 서비스 이용 불가, 갑자기 트래픽이 급증하거나 업데이트 등을 위해 잠시 서버를 다운 시킨 경우 사용

## **HTTP 헤더**

**HTTP 헤더 종류**

- General header
- Request header
- Response header
- Entity header

**General header**

- 요청과 응답 둘 다에서 사용 가능한 일반적인 항목
- 예시
  - `Date` : 메시지가 만들어진 날짜 표시
  - `Cache-Control` : 캐시 관련된 설정 저장

**Request header**

- 요청 프로토콜에서 사용되는, 클라이언트의 정보
- 예시
  - `Cookie` : 서버에 보내는 쿠키 정보
  - `Host` : 요청하는 호스트명
  - `User-Agent` : 클라이언트 스프트웨어(브라우저/OS) 정보
  - `Authorization` : 인증 토큰 정보

**Response header**

- 응답 프로토콜에서 사용되는, 서버의 정보
- 예시
  - `Set-Cookie` : 클라이언트에게 쿠키 정보 전송
  - `Server` : 서버 소프트웨어 정보

**Entity header**

- 바디에 대한 정보를 담고 있음
- 예시
  - `Content-Length` : 메시지 바디 길이 정보
  - `Content-Type` : 메시지 바디의 종류와 인코딩 타입 정보