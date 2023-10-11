# HTTP HEADER

# 정의
- HTTP 헤더는 클라이언트와 서버 사이의 통신에 사용되는 메타데이터.

# 종류
- General Header
    - 모든 종류의 메시지에 사용되는 헤더
- Request Header
    - 요청 메시지에 사용되는 헤더
- Response Header
    - 응답 메시지에 사용되는 헤더
- Entity Header
    - 엔티티 바디에 사용되는 헤더
- Extension Header
    - 표준 명세에 정의되지 않은 헤더, 사용자 정의 헤더

# General Header
### Cache-Control
- 캐싱 동작을 지정
- ex) Cache-Control: no-cache
### Connection
- 네트워크 연결에 대한 옵션을 지정, 기본값은 keep-alive
- ex) Connection: keep-alive
### Date
- 메시지가 발생한 날짜와 시간, 
- ex) Date: Tue, 15 Nov 1994 08:12:31 GMT
### Transfer-Encoding
- 메시지 바디의 전송 코딩 형식을 지정, 여러 개의 전송 코딩 형식을 사용할 수 있음. 모든 서버는 Chunked 전송 코딩을 지원해야 함.
- ex) Transfer-Encoding: chunked

# Request Header
### Accept
- 클라이언트가 처리 가능한 미디어 타입을 서버에 알려줌
- ex) Accept: text/html, application/xhtml+xml, application/xml;q=0.9, image/webp, */*;q=0.8
### Accept-Charset
- 클라이언트가 처리 가능한 문자 인코딩을 서버에 알려줌
- ex) Accept-Charset: utf-8, iso-8859-1;q=0.5
### Accept-Encoding
- 클라이언트가 처리 가능한 압축 인코딩을 서버에 알려줌
- ex) Accept-Encoding: gzip, deflate, br
### Accept-Language
- 클라이언트가 선호하는 자연 언어를 서버에 알려줌
- ex) Accept-Language: ko-KR,ko;q=0.9,en-US;q=0.8,en;q=0.7
### Authorization
- 클라이언트 인증 정보를 서버에 전달
- ex) Authorization: Bearer ********
### Expect
- 클라이언트가 특정 조건이 참이어야만 요청을 서버에 전송
- ex) Expect: 100-continue
### Host
- 요청한 호스트 정보를 서버에 전달
- ex) Host: www.example.com
### TE
- 클라이언트가 이해할 수 있는 전송 코딩 형식을 서버에 알려줌
- ex) TE: trailers, deflate;q=0.5
### User-Agent
- 클라이언트의 애플리케이션 정보를 서버에 전달
- ex) User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64)

# Response Header
### Accept-Ranges
- 서버가 지원하는 리소스의 전송 범위를 알려줌
- ex) Accept-Ranges: bytes
### Age
- 오리진 서버에서 응답을 생성한 후 응답이 공유 캐시에 저장된 시간
- ex) Age: 12
### Allow
- 허용되는 HTTP 메서드를 알려줌
- ex) Allow: GET, HEAD
### Location
- 3xx 응답에서 리다이렉션 대상을 알려줌
- ex) Location: https://www.example.com
### Server
- 서버 애플리케이션 정보를 알려줌
-  ex) Server: Apache/2.4.39 (Win64) OpenSSL/1.1.1b PHP/7.3.6
### Set-Cookie
- 서버에서 클라이언트로 쿠키를 전달
- ex) Set-Cookie: id=a3fWa; Expires=Wed, 21 Oct 2015 07:28:00 GMT; Secure; HttpOnly
### Vary
- 캐시된 응답을 사용할 수 있는 조건을 알려줌
- ex) Vary: Accept-Encoding
### Retry-After
- 503 응답에서 서비스를 사용할 수 있는 시간을 알려줌
- ex) Retry-After: 120

# Entity Header
### Content-Encoding
- 엔티티 바디에 적용된 인코딩을 알려줌
- ex) Content-Encoding: gzip
### Content-Language
- 엔티티 바디에 적용된 자연 언어를 알려줌
- ex) Content-Language: ko-KR
### Content-Length
- 엔티티 바디의 크기를 알려줌
- ex) Content-Length: 1024
### Content-Location
- 엔티티 바디의 대체 위치를 알려줌
- ex) Content-Location: /index.html
### Content-Type
- 엔티티 바디의 미디어 타입을 알려줌
- ex) Content-Type: text/html; charset=utf-8

# Extension Header
### X-Frame-Options
- AJAX 요청을 구별하기 위해 사용되는 헤더입니다.
- ex) X-Frame-Options: SAMEORIGIN
### X-XSS-Protection
- XSS(Cross-Site Scripting) 공격을 방지하기 위해 사용되는 헤더입니다.
- ex) X-XSS-Protection: 1; mode=block
### X-Content-Type-Options
- MIME 스니핑 공격을 방지하기 위해 사용되는 헤더입니다.
- ex) X-Content-Type-Options: nosniff
### X-Content-Security-Policy
- XSS 공격을 방지하기 위해 사용되는 헤더입니다.
- ex) X-Content-Security-Policy: default-src 'self'