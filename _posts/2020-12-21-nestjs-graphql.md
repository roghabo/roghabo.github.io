---
title: "Nest Js에서 GraphQL사용하기"
excerpt: ""

categories:
  - nestjs

tags:
  - nestjs
  - graphql

last_modified_at: 2020-12-22
---

nestjs에서 graphql사용하기 위해서는 아폴로 서버가 필요하다.

### 아폴로 서버 셋업

---

```javascript
npm i @nestjs/graphql graphql-tools graphql apollo-server-express
```

<br><br>

### app.module.ts 설정

---

```javascript
GraphQLModule.forRoot({});
```

- autoSchemaFile: true
  - 이렇게 설정할 경우, 스키마 파일을 만들어 내는데 메모리에는 있으나 직접 파일을 가지고 있지는 않게 됨
