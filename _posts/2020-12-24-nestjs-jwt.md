---
title: "NestJs에서 JWT사용하기"
excerpt: ""

categories:
  - nestjs

tags:
  - nestjs
  - jwt

last_modified_at: 2020-12-24
---

### JWT

---

- jwt란 json web token을 가리킨다.
- 설치
  `npm i jsonwebtoken`
  `npm i @types/jsonwebtoken --only-dev`

<br><br>

### JWT Function

---

- jwt sign

  ```javascript
  import * as jwt from "jsonwebtoken";
  var token = jwt.sign({ foo: "bar" }, privateKey, { algorithm: "RS256" });
  ```

- jwt verify
  ```javascript
  return jwt.verify(token, privateKey);
  ```
  <br><br>

#### 참고 사이트

---

- 랜덤 키 생성  
  <a href="https://randomkeygen.com">secret key generator</a>

- jwt decode  
  <a href="https://jwt.io">jwt</a>
