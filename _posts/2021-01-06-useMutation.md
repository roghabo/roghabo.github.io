---
title: "useMutation"
excerpt: ""

categories:
  - react

tags:
  - react
  - hook

last_modified_at: 2021-01-06
---

### useMutation

---

- mutation을 호출하고 array를 반환함
- `useMutation<TData = any, TVariables = OperationVariables>(호출할 mutation 이름)`

- 받은 mutation의 variables를 변경

  ```typescript
  const [myMutation] = useMutation<>();

  myMutation({
    variables: {
      coffee,
      sugar,
    },
  });
  ```
