---
title: "NestJs GraphQL dynamic field 만들기"
excerpt: ""

categories:
  - javascript

tags:
  - javascript
  - method

last_modified_at: 2021-01-19
---

#### ResolveField()

---

- request가 있을 때 마다 계산해서 보여주는 field
- 계산하기 때문에 entity에 만들지 않고 resolver에 만듦

#### Parent()

---

- 해당 field의 부모를 불러옴

- Ex)

  ```typescript
  @ResolveField('posts')
  async getPosts(@Parent() author) {
      const { id } = author;
      return this.postsService.findAll({ authorId: id });
  }

  ```

  > https://docs.nestjs.com/graphql/resolvers
