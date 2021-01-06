---
title: "Apollo Codegen"
excerpt: ""

categories:
  - apollo

tags:
  - apollo
  - typescript

last_modified_at: 2021-01-06
---

### Apollo Codegen

---

- gql에 대한 static type을 생성함

<br><br>

#### 설치 및 실행

---

- 설치  
   `npm i -g apollo && npm i apollo`

- apollo tooling configure 하기

  - apollo.config.js

    ```javascript
    module.exports = {
      client: {
        includes: ["./src/**/*.tsx"],
        tagName: "gql",
        service: {
          name: "roghabo-service",
          url: "http://localhost:4000/graphql",
        },
      },
    };
    ```

- 실행

  - package.json 파일에 코드 작성
    ```
    "apollo:codegen": " rimraf src/__generated__ && apollo client:codegen src/__generated__ --target=typescript --outputFlat",
    ```
  - 명령어 실행
    `npm run apollo:codegen`

- 결과
  - apollo codegen이 gql을 전달인자로 쓴 변수들의 interface를 제공해줌
  - url을 통해 들어간 backend schema를 보고 return변수와 types를 알려줌

#### globalTypes

---

- apollo codegen 실행 시 globalTypes.ts 파일이 생성 됨
  - 이 파일에는 enum, inputObject가 쓰여짐
