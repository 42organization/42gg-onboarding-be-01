# MVC
### 정의
- Model, View, Controller의 약자로, 소프트웨어 디자인 패턴이다.
### 역할
- Model
    - 데이터아 프로그램의 내부 비즈니스 로직을 담당한다.
- View
    - 사용자에게 보여지는 화면을 구성하는 역할을 한다.
- Controller
    - 사용자의 입력 처리와 흐름 제어를 담당하고, Model과 View를 연결하는 역할을 한다.

### 예시
- 3-Tier-Architecture 에서 프론트엔드는 View, 백엔드는 Model, Controller 역할을 한다.

# MVC 1
- Model1은 JSP가 Controller와 View를 모두 담당한다.
- jsp 페이지에 비즈니스 로직을 처리하기 위한 코드와 웹 브라우저에 결과를 보여주기 위한 출력 관리 코드가 뒤섞여 있는 구조이다.
- 이러한 구조는 유지보수가 어렵고, 코드의 재사용성이 떨어진다는 단점이 있다.

# MVC 2
- 서블릿이 Controller의 역할을 담당한다
- JSP는 View의 역할을 담당한다.
- 비즈니스 로직은 Model에서 처리한다.
