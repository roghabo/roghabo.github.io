---
title: "Mapped Types"
excerpt: ""

categories:
  - nestjs

tags:
  - nestjs
  - graphql

last_modified_at: 2020-12-24
---

### Mapped Types

---

- Base Type을 바탕으로 다른 버전들을 만들어 낼 수 있게 해줌
- Base Type은 InputType이어야 하고, 만들어낸 Mapped Type들도 모두 InputType임
  <br><br>
- 종류

  - Partial Type: 모든 field가 required가 아닌 type을 만들어 줌
  - Pick Type: base type에서 몇 가지 property를 선택해서 새로운 type을 만들어 줌
  - Omit Type: base type에서 몇 가지 property를 제외하고 새로운 type을 만들어 줌
  - Intersection: 두개의 base type을 합쳐줌
    <br><br>

- Base Type이 InputType이 아닐 경우
  - InputType임을 명시해준다.
  - args에 InputType을 써준다.  
    Ex)
    ```typescript
    @InputType
    class CafeDto extends PickType(Cafe, ["menu"], InputType) {}
    ```
