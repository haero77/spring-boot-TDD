# 스프링 부트 TDD - 입문부터 실전까지 정확하게

"스프링 부트 TDD - 입문부터 실전까지 정확하게" 인프런 강의의 실습 코드 저장소입니다.

## 응용프로그램 빌드

```bash
./gradlew build
```

## 응용프로그램 실행

```bash
./gradlew bootRun
```

## API 목록

## 판매자 회원가입

###  요청

- 메서드: POST
- 경로: /seller/signUp
- 헤더 
  ```
  Content-Type: application/json
  ```
- 본문:
  ```
  CreateSellerCommand {
    email: string,
    username: string,
    password: string,
  }
  ```

### 성공 응답

- 상태 코드: 204 No Content

### 정책

- 이메일 주소는 유일해야한다.
- 사용자 이름은 유일해야한다.
- 사용자 이름은 3자 이상의 영문자, 숫자, 하이픈, 밑줄 문자로 구성되어야한다.
- 비밀번호는 8자 이상의 문자로 구성되어야한다.

### 테스트 

- [x] 올바르게 요청하면 204 No Content 상태코드를 반환한다.
- [ ] email 속성이 지정되지 않으면 400을 반환한다.
- [ ] email 속성이 올바른 형식을 따르지 않으면 400을 반환한다.
- [ ] username 속성이 지정되지 않으면 400을 반환한다.
- [ ] username 속성이 올바른 형식을 따르지 않으면 400을 반환한다.
- [ ] password 속성이 지정되지 않으면 400을 반환한다.
- [ ] password 속성이 올바른 형식을 따르지 않으면 400을 반환한다.
- [ ] email 속성에 이미 존재하는 이메일 주소가 지정되면 400을 반환한다.
- [ ] username 속성에 이미 존재하는 사용자 이름이 지정되면 400을 반환한다.
- [ ] 비밀번호를 올바르게 암호화한다.

### 판매자 회원가입 API curl 명령 

```
curl -i -X POST 'http://localhost:8080/seller/signUp' \
-H 'Content-Type: application/json' \
-d '{
  "email": "seller1@example.com",
  "username": "seller1",
  "password": "seller1-password"
}'
```
