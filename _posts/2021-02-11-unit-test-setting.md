---
title: "Unit Test 하기 전 Setting"
excerpt: "unit test setting"

categories:
  - unit test

tags:
  - typescript
  - unit test

last_modified_at: 2021-02-11
---

### Unit Test

##### 파일 만들기

---

- .spec.ts로 끝나는 파일
  <br>
  <br>

##### 경로 문제

---

- jest는 상대경로만 파악하기 때문에 설정을 해줘야 함
- package.json
  ```json
  "jest": { "moduleNameMapper": { "^src/(.*)$" : "<rootDir>/$1" } }
  ```
  <br>
  <br>

##### 명령어

---

1. `npm run test:watch`
   - 테스트 진행 결과를 보여줌
2. `npm run test:cov`
   - 모든 코드의 테스트가 어디까지 커버되고 있는지 보여줌
     <br>
     <br>

##### coverage 제한하기

---

- package.json

  ```json
  "coveragePageIgnorePatterns":[
      "node_modules",
      ".entity.ts",
      ".constants.ts"
  ]
  ```
