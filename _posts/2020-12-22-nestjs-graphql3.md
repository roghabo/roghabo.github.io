---
title: "ArgsType 검증 사용하기"
excerpt: ""

categories:
  - nestjs

tags:
  - nestjs
  - graphql

last_modified_at: 2020-12-22
---

- 설치하기

  ```javascript
    npm i class-validator class-transformer
  ```

  <br>

- main.ts 설정하기

  ```javascript
  app.useGlobalPipes(new ValidationPipe());
  ```
