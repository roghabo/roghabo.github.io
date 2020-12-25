---
title: "Graphql Context"
excerpt: ""

categories:
  - nestjs

tags:
  - nestjs
  - graphql

last_modified_at: 2020-12-25
---

### Context

---

- context가 function으로 정의되면 request 할 때마다 불려진다.
- context가 'req' object에 포함되어, 값을 받을 수 있다.
- Ex)
  app.module.ts
  ```typescript
  GraphQLModule.forRoot({
    context: ({ req }) => ({ cafe: req["cafe"] }),
  });
  ```
  <br><br>

### Context값 사용하기

---

- Ex)
  ```typescript
  call(@Context() context) {
      if(!context.cafe) {
          return;
      } else {
          return context.cafe;
      }
  }
  ```
