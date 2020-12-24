---
title: "TypeORM @Entity(), @Column()"
excerpt: ""

categories:
  - nestjs

tags:
  - nestjs
  - typeorm

last_modified_at: 2020-12-24
---

### Entity

---

- entity: 데이터베이스에서 저장되는 데이터의 형태를 보여줌
  <br><br>

- ##### @Entity()

  - typeorm이 db에 저장하게 해줌

  <br><br>

- ##### @Column()
  - 열을 만들어줌
    <br><br>

### TypeOrm에게 만든 Entity 위치 알려주기

---

- app.module.ts

  ```javascript
  TypeOrmModule.forRoot({
      entities: [ 엔티티 이름 ]
  }),
  ```
