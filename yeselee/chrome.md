### **크롬 개발자도구**

**크롬 개발자도구란**

- 웹사이트의 다양한 요소를 검사하고 테스트할 수 있는 도구
- 여러 개의 패널 존재(element, console, network, application 등)

**Elements**

- html, css 를 확인할 수 있음
- 왼쪽에서 html 태그 확인
- Styles 패널 에서 모든 css 확인 가능
- Computed 패널에서 최종 적용된 css 확인 가능

**Console**

- 콘솔 창, 자바스크립트 코드 실행 가능
- `console.log()` 로 개발하며 로그를 찍어볼 수 있음

**Network**

- 웹사이트에서 통신하고 있는 모든 정보를 보여줌
- 백엔드와 프론트엔드의 네트워크 통신이 제대로 이루어졌는지 확인할 때 유용함
- 타입 별로 나눠서 확인할 수 있음
    - `Fetch/XHR 탭` 에서 api 요청/응답에 관한 정보를 확인할 수 있음
        - preview - 받아온 api 정보를 json 형식으로 확인 가능 (response 를 좀 더 보기 편하게 해 둔 것)

**Application**

- 브라우저 저장소의 내용 확인 가능
- `Local storage, Session storage, cookie` 3개의 저장소가 있음
- cookie
    - 클라이언트 단에 저장
    - 4kb의 용량 제한이 있음
    - 매번 서버로 전송됨
- Web Storage
    - 해당 도메인과 관련된 특정 데이터를 클라이언트 웹 브라우저에 저장하는 기능
    - 쿠키의 단점 보완
    - `Local storage` 와 `Session Storage` 두 종류가 있음

      Local Storage : 영구 저장소, 브라우저를 닫았다 열어도 유지됨

      Session Storage : 브라우저를 닫으면 삭제