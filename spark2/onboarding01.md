# 10/10 화

온보딩 1주차

## 개발 환경 세팅

- `Intellij` 세팅 (JetBrains 사의 IntelliJ IDEA)
    - Java 진영의 개발툴(IDE)
- `MySQL` 설치
    - 가장 널리 사용되고 있는 **관계형** 데이터베이스 관리 시스템(RDBMS: Relational DBMS)
    - `SQL`: 관계형 데이터베이스에 정보를 저장하고 처리하기 위한 프로그래밍 언어
- `redis` 설치
    - **Key, Value** 구조의 비정형 데이터를 저장하고 관리하기 위한 오픈 소스 기반의 **비관계형** 데이터 베이스 관리 시스템 (DBMS)
    - 캐시!라고 이해하기 (빠름)
    - 데이터가 많으면 사용하기 곤란

## 간단 이론 공부

### `HTTP`란? (HyperText Transfer Protocol)

- 텍스트 기반의 통신 규약으로 **인터넷에서 데이터를 주고받을 수 있는 프로토콜**
- 특정 상태를 유지하지 않는 무상태성(Stateless)이 특징 → 요청과 응답 이후, 이전 데이터 휘발됨
- ex) 우리가 웹 브라우저의 주소창에 https://www.naver.com을 입력하고 Enter 를 누르면 웹 클라이언트와 웹 서버 사이에 HTTP 연결이 맺어지고 웹 클라이언트는 웹 서버에 HTTP 요청 메시지를 보냅니다. 웹 서버는 요청에 따른 처리를 진행한 후에 그 결과를 웹 클라이언트에 HTTP 응답 메시지로 보냅니다. 이처럼 요청 메시지와 응답 메시지가 반복적으로 오가므로 우리는 웹을 사용할 수 있는 것입니다.

    <img width="549" alt="1" src="https://github.com/Newsujin/42gg-onboarding-be-01/assets/104690611/f0e3a376-1618-43c8-9639-9988fb4605c3">
    
- `HTTP Method`
    - 클라이언트와 서버 사이에 이루어지는 요청(Request)과 응답(Response) 데이터를 전송하는 방식
    - 종류
        - 주요 메소드
            - **GET :** 리소스 조회
            - **POST:**  요청 데이터 처리, 주로 등록에 사용
            - **PUT :** 리소스를 대체(덮어쓰기), 해당 리소스가 없으면 생성
            - **PATCH :** 리소스 부분 변경 (PUT이 전체 변경, PATCH는 일부 변경)
            - **DELETE :** 리소스 삭제
        - 기타 메소드
            - **HEAD :** GET과 동일하지만 메시지 부분(body 부분)을 제외하고, 상태 줄과 헤더만 반환
            - **OPTIONS :** 대상 리소스에 대한 통신 가능 옵션(메서드)을 설명(주로 CORS에서 사용)
            - **CONNECT :** 대상 자원으로 식별되는 서버에 대한 터널을 설정
            - **TRACE :** 대상 리소스에 대한 경로를 따라 메시지 루프백 테스트를 수행
    - **`멱등성`(idempotent)이란?**
        - 전산학이나 수학에서 사용하는 용어로 **연산을 여러 번 적용하더라도 결과가 달라지지 않는 성질**, **연산을 여러 번 반복하여도 한 번만 수행된 것과 같은 성질**을 의미한다.
- `HTTP Status Code` (상태 코드 표)
    - 서버에서의 처리 결과는 응답 메시지의 상태 라인에 있는 상태 코드(status code)를 보고 파악할 수 있다.
    - 상태 코드는 세 자리 숫자로 구성
        - 첫 번째 숫자는 HTTP 응답의 종류를 구분
        - 나머지 2개의 숫자는 세부적인 응답 내용 구분
    - 현재 100~500번 대까지 상태 코드가 정의되어 있는데, 첫 번째 자리 숫자에 따라 다음과 같이 **5가지**로 분류
        - **1XX: Informational(정보 제공)**
            - 임시 응답으로 현재 클라이언트의 요청까지는 처리되었으니 계속 진행하라는 의미입니다. HTTP 1.1 버전부터 추가되었습니다.
        - **2XX: Success(성공)**
            - 클라이언트의 요청이 서버에서 성공적으로 처리되었다는 의미입니다.
        - **3XX: Redirection(리다이렉션)**
            - 완전한 처리를 위해서 추가 동작이 필요한 경우입니다. 주로 서버의 주소 또는 요청한 URI의 웹 문서가 이동되었으니 그 주소로 다시 시도하라는 의미입니다.
        - **4XX: Client Error(클라이언트 에러)**
            - 없는 페이지를 요청하는 등 클라이언트의 요청 메시지 내용이 잘못된 경우를 의미합니다.
        - **5XX: Server Error(서버 에러)**
            - 서버 사정으로 메시지 처리에 문제가 발생한 경우입니다. 서버의 부하, DB 처리 과정 오류, 서버에서 익셉션이 발생하는 경우를 의미합니다.
- `HTTP 헤더`
    - HTTP 공통 헤더
        - HTTP 헤더 내 일반 헤더 항목
        - 요청 및 응답 메시지 모두에서 사용 가능한 일반 목적의(기본적인) 헤더 항목
    - HTTP 엔티티 관련 헤더
        - HTTP 헤더 내 엔터티/개체 헤더 (Entity Header) 항목
        - 바디의 길이를 명시하는 헤더
        - 요청 및 응답 메시지 모두에서 사용 가능한 Entity(콘텐츠, 본문, 리소스 등)에 대한 설명 헤더 항목
    - HTTP 요청 헤더
        - HTTP 헤더 내 요청 헤더 (Request Header) 항목
        - 요청 헤더는 HTTP 요청 메시지 내에서만 나타나며 가장 방대하다.
     
    
        <img width="664" alt="2" src="https://github.com/Newsujin/42gg-onboarding-be-01/assets/104690611/2a364bb8-e239-411a-b8a5-4ba20bd4654a">

            
    - HTTP 응답 헤더
        - HTTP 헤더 내 응답 헤더 (Response Header) 항목
        - 특정 유형의 HTTP 요청이나 특정 HTTP 헤더를 수신했을 때, 이에 응답한다.
    - HTTP 캐시 / 쿠키 관련 헤더

### 개발자 도구 (DevTools)란?

- 개발자들이 홈페이지를 수정하고 발생한 문제의 원인을 쉽게 파악하기 위해 브라우저에서 제공하는 도구
- 개발자 도구 **단축키**
    - window : `f12`
    - mac : `alt` + `cmd` + `i`
- 개발자 도구 패널 (DevTools paner)
    1. Elements panel
        
        <img width="697" alt="3" src="https://github.com/Newsujin/42gg-onboarding-be-01/assets/104690611/5de18988-ef22-49d3-85c7-23c0f6ce283f">

        - 개발자 도구의 기본 탭
        - 웹페이지의 구성(DOM), CSS 알 수 있다.
        - HTML 코드를 분석하고 실시간으로 수정할 수 있는 패널. 실시간으로 레이아웃과 디자인을 변경할 수 있다.
    2. Console panel
        
        <img width="750" alt="4" src="https://github.com/Newsujin/42gg-onboarding-be-01/assets/104690611/1befaeab-a08c-4f5f-9218-a524eaafc3c4">

        - 컴퓨터의 키보드&마우스, 오락기의 조이스틱 같이 **동작하기 위한 패널**
        - 따라서 브라우저가 어떻게 동작하는지 조절하는 패널
        - 여기서 자바스크립트 코드를 즉시 실행할 수 있다.
        - **브라우저 콘솔창에 로그를 찍는다(`console.log()`)**고 표현
    3. Network panel ⭐️(개발자들이 프로젝트할 때 무조건 봐야하는 공간)
        
        <img width="745" alt="5" src="https://github.com/Newsujin/42gg-onboarding-be-01/assets/104690611/c84cbd5a-2527-471f-b5fe-4907ff7a2c0c">

        - 웹사이트에서 **통신하고 있는 모든 정보**를 목록으로 보여준다.
        - 리소스들이 예상대로 다운로드 되고 업데이트 되는지 확인할 때 사용한다.
        - 웹페이지와 서버 사이에서 데이터 흐름을 분석하고, 문제 발생 시 해결책을 찾도록 개발자를 돕는 역할을 한다.
    4. Application panel
        
        <img width="754" alt="6" src="https://github.com/Newsujin/42gg-onboarding-be-01/assets/104690611/fd6814db-4c84-4b54-a7e4-7cc1e7ed815e">

        - 브라우저 저장소이다.
        - 3개의 브라우저 저장소(Storage) 존재
            - **Local Storage** ⇒ 클라이언트 단 사용자가 지우지 않는 이상 계속 브라우저에 남아있다. 지속적으로 필요한 데이터를 저장한다.
            예) 자동로그인 기능
            - **Session Storage** ⇒ 클라이언트 단 브라우저 종료 전까지만 보존 가능 ⇒ 탭 종료 전까지 남아있다. 잠깐 동안 필요한 정보를 저장.
            예) 비회원 장바구니
            - **Cookie** ⇒ 클라이언트에 저장되지만 서버에서도 리스폰스를 보낼 수 있다. 저장 용량이 작다. 시간 제한 설정이 가능. 프론트엔드와 백엔드 통신과 관련 있다. 무조건 요청 보낼 때마다 딸려서 간다.
            예) 오늘만 하는 이벤트 팝업, 서비스 약관에 동의했는지 등 팝업창 1일동안 보지않기 버튼을 누르면 안 보겠다는 것을 저장, 만료기간 세팅 가능 ⇒ 1일짜리 쿠키를 만들어놓으면 됩니다.