---
title: "Apollo Reactive variables"
excerpt: ""

categories:
  - apollo

tags:
  - apollo

last_modified_at: 2021-01-03
---

### Reactive variables

---

- 아폴로 클라이언트 캐시 외부에 로컬 상태를 저장하는 데 유용한 메커니즘
- 캐시와 분리되기 때문에 모든 유형 및 구조의 데이터를 저장할 수 있으며, GraphQL 구문을 사용하지 않고도 애플리케이션 내 어디에서나 이 변수와 상호 작용할 수 있음.
- 수정 시 해당 변수에 종속된 모든 활성 쿼리의 업데이트와 'useReactiveVar'에서 반환된 변수 값과 관련된 반응 상태의 업데이트가 트리거된다.

<br><br>

#### Reactive variables 생성, 읽기, 수정

---

```typescript
import { makeVar } from "@apollo/client";

const checkWantCoffee = makeVar(false); //create
console.log(checkWantCoffee()); //read
checkWantCoffee(true); //modify
```

<br><br>

#### useReactiveVar 사용

---

```typescript
import { useReactiveVar } from "@apollo/client";

const wantCoffee = useReactiveVar(CheckWantCoffee);
return wantCoffee ? "Yes, coffee please" : "No thanks";
```
