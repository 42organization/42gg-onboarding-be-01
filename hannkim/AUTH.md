# 인증 vs 인가

## 인증 (Authentication)

- 신원 확인하는 과정
- ex) 회원가입, 로그인
- 인증 절차를 통해 Access Token 발급

## 인가 (Authorization)

- 사용자가 요청하는 요청을 실행할 수 있는 권한 여부 확인하는 절차
- 리소스에 접근할 수 있는지 또는 어떤 동작을 수행할 수 있는지를 검증하는 것
- 접근 권한 부여하거나 거부하는 행위
- 사용자의 요청에 담긴  Access Token을 복호화하고 DB에서 사용자 권한 확인