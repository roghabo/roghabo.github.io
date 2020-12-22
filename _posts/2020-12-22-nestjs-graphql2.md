---
title: "ObjectType, InputType, ArgsType"
excerpt: ""

categories:
  - nestjs

tags:
  - nestjs
  - graphql

last_modified_at: 2020-12-22
---

<h3>@ObjectType()</h3>

---

- @ObjectType()은 자동으로 스키마를 생성하기 위해 사용하는 graphql decorator임
  <br><br>

<h3>@InputType()</h3>

---

- @InputType()은 object를 통째로 전달할 수 있게 해줌
- object arguments를 받아 graphql로 전달해 줌

<br>

- InputType을 사용하지 않았을 때

  ```javascript
  cafe(
    @Args('coffee') coffee:string,
    @Args('milk') milk:string,
    @Args('water') water:string,
  ): boolean {
    return: true;
  }
  ```

<br>

- InputType을 사용했을 때

  ```javascript
  cafe(
    @Args('cafe') cafe:CafeDto,
  ): boolean {
    return: true;
  }
  ```

<br><br>

<h3>@ArgsType()</h3>

---

- @ArgsType()은 분리된 값들을 graphql argument에 전달해줌

- Ex)
  ```javascript
  cafe(
    @Args() cafe:CafeDto,
  ): boolean {
    return: true;
  }
  ```
