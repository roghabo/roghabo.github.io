---
title: "TypeOrm을 이용하여 Repository사용"
excerpt: ""

categories:
  - nestjs

tags:
  - nestjs
  - typeorm
  - postgresql

last_modified_at: 2020-12-24
---

### Repository

---

- db에 접근하기 위해 Data Mapper방법을 사용하면 repository를 이용한다.
  <br>

- repository: entity랑 상호작용하는 것을 담당함
  <br>

- Repository가 필요한 module에서 import해야 함
  .module.ts

  ```typescript
  @Module({
      imports: [TypeOrmModule.forFeature([엔티티 클래스])],
  })
  ```

  <br>

  - 이렇게 해주면 .service.ts, .resolver.ts 파일에서 repository 접근 가능  
    Ex)
    <br>
    .service.ts

    ```typescript
    export class CafeService {
      constructor(@InjectRepository(Cafe) cafes: Repository<Cafe>) {}
    }
    ```
