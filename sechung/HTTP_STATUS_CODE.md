# HTTP_STATUS_CODE

# 정의
- HTTP STATUS CODE는 HTTP 요청에 대한 응답의 상태를 나타내는 3자리 숫자이다.

# 종류
- 1xx : 요청이 수신되어 처리중, 계속 진행하라는 의미
- 2xx : 요청 정상 처리
- 3xx : 요청을 완료하려면 추가 행동이 필요
- 4xx : 클라이언트 오류
- 5xx : 서버 오류

# 1xx
### 100 Continue
- 요청의 시작 부분을 서버가 받았으며 나머지를 계속 받을 수 있음을 알려준다.
### 101 Switching Protocols
- 서버가 클라이언트의 요청을 받아들이고 프로토콜을 전환할 것임을 알려준다.
### 102 Processing
- 서버가 요청을 수신하여 처리 중이지만, 긴 시간이 예상됨을 클라이언트에게 알려준다.

# 2xx
### 200 OK
- 요청이 성공적으로 되었음을 의미한다.
### 201 CREATED
- 요청이 성공적으로 되었으며 새로운 리소스가 생성되었음을 의미한다.
### 203 Non-Authoritative Information
- 요청이 성공적으로 되었으며, 응답에 포함된 정보는 오리진 서버에서 가져온 것이 아님을 의미한다.
### 204 No Content
- 요청은 성공적이었지만, 클라이언트에게 보낼 콘텐츠가 없음을 의미한다.
### 205 Reset Content
- 요청이 성공적으로 되었으며, 클라이언트는 페이지를 리셋해야 함을 의미한다.
### 206 Partial Content
- 요청이 성공적으로 되었으며, 응답에 부분적인 콘텐츠가 포함되어 있음을 의미한다.
- Content-Range에 응답 콘텐츠의 범위가 포함되어 있다.
### 207 Multi-Status
- 처리 결과의 상태가 여러 개임을 의미, 성공을 의미하지만 각각의 성공여부는 별도로 확인해야 한다.

# 3xx
### 300 Multiple Choices
- 요청에 대해 여러 응답 중 하나를 선택할 수 있음을 의미한다.
### 301 Moved Permanently
- 요청한 리소스가 새로운 URI로 변경되었음을 의미한다.
### 302 Found
- 요청한 리소스의 URI가 일시적으로 변경되었음을 의미한다.
### 303 See Other
- 요청에 대한 응답이 다른 URI에 있음을 의미한다.
### 304 Not Modified
- 클라이언트가 마지막으로 요청한 이후에 요청한 리소스가 수정되지 않았음을 의미한다.
- 계속해서 응답의 캐시된 버전을 사용할 수 있다는 것을 의미
### 305 Use Proxy
- 요청한 응답은 반드시 프록시를 통해서 접속해야 함을 의미
### 306 Unused
- 현재는 사용되지 않음
### 307 Temporary Redirect
- 요청에 대한 응답이 일시적으로 다른 URI에 있음을 의미한다.
- 302와 다르게 요청 메소드가 변경되지 않는다.
### 308 Permanent Redirect
- 요청에 대한 응답이 영구적으로 다른 URI에 있음을 의미한다.
- 301과 다르게 요청 메소드가 변경되지 않는다.

# 4xx
### 400 Bad Request
- 잘못된 문법으로 서버가 이해할 수 없음을 의미한다.
### 401 Unauthorized
- 인증이 필요함을 의미한다.
### 402 Payment Required
- 디지털 결제 시스템을 위해 만들어졌지만 현재는 사용되지 않음
### 403 Forbidden
- 서버가 요청을 거부함을 의미한다.
- 401과 다른점은 클라이언트가 누군지 안다는 것이다.
### 404 Not Found
- 요청한 리소스가 서버에 없음을 의미한다.
### 405 Method Not Allowed
- 요청한 메소드가 허용되지 않음을 의미한다.
### 406 Not Acceptable
- 콘텐츠 협상에 실패했음을 의미한다.
### 407 Proxy Authentication Required
- 프록시 서버에서 인증이 필요함을 의미한다.
### 408 Request Timeout
- 요청 시간이 초과되었음을 의미한다.
### 409 Conflict
- 요청이 서버의 현재 상태와 충돌함을 의미한다.
### 410 Gone
- 요청한 리소스가 서버에서 영구적으로 삭제되었음을 의미한다.
### 411 Length Required
- Content-Length 헤더가 요청에서 정의되지 않았음을 의미한다.
### 412 Precondition Failed
- 클라이언트 요청의 전제 조건이 실패함을 의미한다.
### 413 Payload Too Large
- 요청 페이로드가 서버에서 정의한 한계를 초과함을 의미한다.
### 414 URI Too Long
- 요청 URI가 서버에서 정의한 한계를 초과함을 의미한다.
### 415 Unsupported Media Type
- 요청이 지원되지 않는 미디어 타입임을 의미한다.
### 416 Requested Range Not Satisfiable
- 범위가 타겟 URI의 크기를 벗어난 것을 의미한다.
### 417 Expectation Failed
- 요청의 Expect가 서버에서 만족되지 않음을 의미한다.
### 418 I'm a teapot
- 서버는 커피를 찻 주전자에 끓이는 것을 거부함을 의미한다.
### 421 Misdirected Request
- 클라이언트의 요청이 잘못된 서버로 전달되었음을 의미한다. 요청을 처리할 수 없거나 처리하면 프로토콜을 위반하게 될 때 발생한다.
### 422 Unprocessable Entity
- 서버가 요청을 이해했지만, 요청을 처리할 수 없음을 의미한다.
### 423 Locked
- 리소스가 현재 잠겨있음을 의미한다.
### 424 Failed Dependency
- 이전 요청이 실패했기 때문에 현재 요청이 실패함을 알려준다.
### 426 Upgrade Required
- 클라이언트가 요청한 리소스를 얻기 위해서는 업그레이드가 필요함을 의미한다.
### 428 Precondition Required
- 서버가 요청을 처리하기 위해서는 요청에 조건이 필요함을 의미한다.
### 429 Too Many Requests
- 클라이언트가 지정된 시간 내 너무 많은 요청을 보냄을 의미한다.
### 431 Request Header Fields Too Large
- 요청 헤더가 서버에서 정의한 한계를 초과함을 의미한다.
### 451 Unavailable For Legal Reasons
- 리소스에 대한 접근이 정부에 의해 검열되어 금지됨을 의미한다.

# 5xx
### 500 Internal Server Error
- 서버가 요청을 처리할 수 없음을 의미한다.
### 501 Not Implemented
- 서버가 요청을 처리할 기능을 제공하지 않음을 의미한다.
### 502 Bad Gateway
- 서버가 게이트웨이로부터 잘못된 응답을 받았음을 의미한다.
### 503 Service Unavailable
- 서버가 요청을 처리할 준비가 되지 않았음을 의미한다. (과부화, 유지보수 등)
### 504 Gateway Timeout
- 서버가 게이트웨이로부터 적시에 응답을 받지 못했음을 의미한다.
### 505 HTTP Version Not Supported
- 서버가 요청에 사용된 HTTP 프로토콜 버전을 지원하지 않음을 의미한다.
### 506 Variant Also Negotiates
- 서버가 내부 구성 오류로 인해 적절한 표현을 찾지 못함을 의미한다.
### 507 Insufficient Storage
- 서버가 요청을 처리하기 위한 충분한 공간을 가지고 있지 않음을 의미한다.
### 508 Loop Detected
- 서버가 요청을 처리하는 동안 무한 루프에 빠졌음을 의미한다.
### 510 Not Extended
- 서버가 요청에 필요한 확장 기능을 지원하지 않음을 의미한다.
### 511 Network Authentication Required
- 네트워크 액세스를 위해 인증이 필요함을 의미한다.