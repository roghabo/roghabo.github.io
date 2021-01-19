---
title: "@RelationId"
excerpt: ""

categories:
  - typeorm

tags:
  - typeorm
  - relation

last_modified_at: 2021-01-19
---

#### @RelationId

---

- @RelationId((엔티티: 엔티티타입) =>누구의 relation id인지 명시)
- relation의 id를 로드 함

- Ex)

  ```typescript
  @Entity()
  export class Post {
    @ManyToOne((type) => Category)
    category: Category;

    @RelationId((post: Post) => post.category) // you need to specify target relation
    categoryId: number;
  }
  ```

  > https://github.com/typeorm/typeorm/blob/master/docs/decorator-reference.md#relationid
