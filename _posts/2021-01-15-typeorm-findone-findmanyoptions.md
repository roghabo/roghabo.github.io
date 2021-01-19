---
title: "Typeorm find-options"
excerpt: ""

categories:
  - typeorm

tags:
  - typeorm

last_modified_at: 2021-01-15
---

- TypeORM은 DB relationship을 자동으로 처리하지 못함
  -> 따로 요구해야만 가져올 수 있음

- id만 가져오는 방법

  ```typescript
  await this.users.findOne({ loadRelationIds: true });
  ```

- class통째로 가져오는 방법
  ```typescript
  await this.users.findOne({ relations: true });
  ```
