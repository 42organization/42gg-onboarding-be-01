# Synchronized
### 정의
- 멀티 스레드 환경에서 스레드 간의 동기화를 관리하기 위해 사용된다.
- synchronized 키워드를 사용하면, 해당 메소드나 블록을 한번에 하나의 스레드만 실행할 수 있도록 보장한다.
- 공유 데이터를 여러 스레드가 동시에 수정하는 것을 방지하여 데이터 무결성을 보호할 수 있다.

### 사용법
- synchronized 키워드를 메소드 선언부에 붙이거나, 메소드 내부에 synchronized 블록을 사용한다.
    - 메소드 선언부: public synchronized void method() { ... }
    - 메소드 내부: sychronized (this) { ... }

### 주의 사항
- 성능이 저하될 수 있다.
    - synchronized 메서드나 블록은 한번에 하나의 스레드만 실행할 수 있도록 보장한다.
    - 이는 당연히 멀티 스레딩의 장점을 살리지 못하게 된다.
    - 남용하면 안되며 필요한 부분에만 사용해야 한다.
- Deadlock에 주의해야 한다.
    - 예시: 두 스레드가 동시에 A, B 객체의 synchronized 메서드를 호출하고, A 객체의 메서드에서 B 객체의 synchronized 메서드를 호출하고 B 객체의 메서드에서 A 객체의 synchronized 메서드를 호출하는 경우 데드락이 걸릴 것이다. 
- Object level lock
    - 메서드에 synchronized 키워드를 사용하면, 해당 메서드를 소유한 객체에 lock이 걸린다.
    - 즉 해당 인스턴스의 다른 synchronized 메서드도 전부 lock이 걸린다.