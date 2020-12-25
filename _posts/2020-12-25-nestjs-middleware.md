---
title: "NestJs Middleware"
excerpt: ""

categories:
  - nestjs

tags:
  - nestjs
  - middleware

last_modified_at: 2020-12-25
---

### NestJs Middleware 작성

---

- nestjs의 middleware는 express의 middleware와 동일함
- request, response objects가 있고 next() 함수 사용
- Ex)

  - function 타입

    ```typescript
    import { Request, Response, NextFunction } from "express";

    export function Middleware(
      req: Request,
      res: Response,
      next: NextFunction
    ) {
      console.log("middleware");
      next();
    }
    ```

  - class 타입

    ```typescript
    import { NestMiddleware } from "@nestjs/common";
    import { NextFunction, Request, Response } from "express";
    class Middleware implements NestMiddleware {
      use(req: Request, res: Response, next: NextFunction) {
        console.log("middleware");
        next();
      }
    }
    ```

    <br><br>

### Middleware 사용하기

---

- Ex1) app.module.ts

  ```typescript
  export class AppModule {
    configure(consumer: MiddlewareConsemer) {
      consumer.apply(jwtMiddleware).forRoute({
        path: "*",
        method: RequestMethod.ALL,
      });
    }
  }
  ```

  - forRoute: 어떤 라우트에서 middleware를 사용할지 설정
    (exclude사용시 특정 path만 제외하고 설정 가능)

- Ex2) main.ts
  ```typescript
  app.use(사용할 미들웨어)
  ```
  - 이 경우는 functional middleware만 사용 가능
