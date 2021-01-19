---
title: "@ManyToMany"
excerpt: ""

categories:
  - typeorm

tags:
  - typeorm
  - relation

last_modified_at: 2021-01-19
---

#### @ManyToMany

---

- 다대다의 관계
- Many-to-many에서는 @JoinTable()이 필수적이다. 두군데 중 소유하고 있는 쪽의 relation에 추가하면 된다.
- Ex)

  ```typescript
  @Entity()
  export class Category {
    @PrimaryGeneratedColumn()
    id: number;

    @Column()
    name: string;
  }
  ```

  ```typescript
  @Entity()
  export class Question {
    @PrimaryGeneratedColumn()
    id: number;

    @Column()
    title: string;

    @ManyToMany(() => Category)
    @JoinTable()
    categories: Category[];
  }
  ```

  > https://typeorm.io/#/many-to-many-relations
