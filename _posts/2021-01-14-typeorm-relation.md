---
title: "@OneToMany & @ManyToOne"
excerpt: ""

categories:
  - typeorm

tags:
  - typeorm
  - relation

last_modified_at: 2021-01-14
---

#### @OneToMany, @ManyToOne

---

- 일대다, 다대일의 관계
- 예를 들어, 한 사람이 많은 사진을 가지고 있다.  
  사람 쪽이 @OneToMany(필드타입, 연결된 필드)  
  사진 쪽이 @ManyToOne(필드타입, 연결된 필드)
- Ex)

  ```typescript
  import { Entity, PrimaryGeneratedColumn, ManyToOne } from "typeorm";
  import { User } from "./User";

  @Entity()
  export class Photo {
    @PrimaryGeneratedColumn()
    id: number;

    @ManyToOne(() => User, (user) => user.photos)
    user: User;
  }
  ```

  ```typescript
  import { Entity, PrimaryGeneratedColumn, OneToMany } from "typeorm";
  import { Photo } from "./Photo";

  @Entity()
  export class User {
    @PrimaryGeneratedColumn()
    id: number;

    @OneToMany(() => Photo, (photo) => photo.user)
    photos: Photo[];
  }
  ```

  > https://typeorm.io/#/many-to-one-one-to-many-relations
