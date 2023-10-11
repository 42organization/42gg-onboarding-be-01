데이터 패킷 전송 방법
=======

IP(인터넷 프로토콜)란?
-----

### IP(인터넷 프로토콜)의 역할

1. 지정한 IP주소에 데이터 전달
2. 패킷이라는 통신 단위로 전달

### IP 패킷 정보

<img width="343" alt="image" src="https://github.com/kokomong2/42gg-onboarding-be-01/assets/105098279/ff7a778e-4e81-4c3c-994d-5908f61b6754">

### 전송 과정

<img width="541" alt="image" src="https://github.com/kokomong2/42gg-onboarding-be-01/assets/105098279/7af626d8-0030-4524-9443-3a77c10c76eb">


### IP 패킷의 한계

1. 비연결성
  - 패킷을 받을 대상이 없거나 서비스 불능 상태여도 패킷 전송
2. 비신뢰성
  - 중간에 패킷이 사라지면?
  - 패킷이 순서대로 안오면? 프로그램 구분
  - 같은 IP를 사용하는 서버에서 통신하는 애플리케이션이 둘 이상이면?

TCP란?
----

- 전송 제어 프로토콜(Transmission Control Protocol, TCP, 문화어: 전송조종규약)은 인터넷 프로토콜 스위트(IP)의 핵심 프로토콜 중 하나로, IP와 함께 TCP/IP라는 명칭으로도 널리 불린다.

- 연결지향 - TCP 3 way handshake (가상 연결) 데이터 전달 보증
- 순서 보장
- 신뢰할 수 있는 프로토콜 현재는 대부분 TCP 사용

### TCP 패킷

<img width="343" alt="image" src="https://github.com/kokomong2/42gg-onboarding-be-01/assets/105098279/9ae6eca1-5eff-494c-b8ff-0203f640bfe8">

### 전송 과정

<img width="541" alt="image" src="https://github.com/kokomong2/42gg-onboarding-be-01/assets/105098279/787e5f69-8851-4a38-b7ee-537b802a25af">


최근에는 UDP를 사용하기도 함 (http 3버전)

HTTP란
=====

- HTML 문서와 같은 리소스들을 가져올 수 있도록 해주는 프로토콜
- HTML, TEXT
- IMAGE, 음성, 영상, 파일
- JSON, XML (API)
- 거의 모든 형태의 데이터 전송 가능
- 서버간에 데이터를 주고 받을 때도 대부분 HTTP 사용

HTTP 메시지

<img width="500" alt="image" src="https://github.com/kokomong2/42gg-onboarding-be-01/assets/105098279/cf851c6e-b504-49ae-a8bd-4a0e2385e2ec">


### 시작 라인 요청 메시지

```
GET /search?q=hello&hl=ko HTTP/1.1
```

HTTP 메서드 (GET: 조회)
요청 대상 (/search?q=hello&hl=ko) 
HTTP Version

### 시작 라인 응답 메시지
```
HTTP/1.1 200 OK
```
1. HTTP 버전
2. HTTP 상태 코드: 요청 성공, 실패를 나타냄
   
• 200: 성공  
• 400: 클라이언트 요청 오류  
• 500: 서버 내부 오류  

### HTTP 헤더 용도


1. HTTP 전송에 필요한 모든 부가정보
- 예) 메시지 바디의 내용, 메시지 바디의 크기, 압축, 인증, 요청 클라이언트(브라우저) 정보, 서버 애플리케이션 정보, 캐시 관리 정보...


### HTTP 바디 용도


1. 실제 전송할 데이터
2. HTML 문서, 이미지, 영상, JSON 등등 byte로 표현할 수 있는 모든 데이터 전송 가능  
json 예 )
```
{ "name" : "Jaxon" , "age" : "42" , "city" , "New York" }
```

HTTP 메서드
----

