---
title: "NestJS Guard"
excerpt: ""

categories:
  - javascript

tags:
  - javascript
  - method

last_modified_at: 2021-01-15
---

##### SetMetadata

---

- metadata를 set함
- SetMetadata(key, value)

##### APP_GUARD

---

- nestjs에서 제공하는 constants
- gurad를 모든 앱에서 사용하고 싶으면 APP_GUARD를 provide해주면 된다.
- Ex)
  ```typescript
  @Module({
      providers:[
          {
              provide: APP_GUARD,
              useClass: AuthGuard,
          }
      ]
  })
  ```
