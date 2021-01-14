---
title: "TypeORM Relation Options (onDelete, nullable)"
excerpt: ""

categories:
  - typeorm

tags:
  - typeorm
  - relation

last_modified_at: 2021-01-14
---

##### onDelete

---

- 삭제 시 데이터베이스에서 종속적으로 일어날 액션
- delete types ( Ex - 사진을 가지고 있는 주인을 삭제하면)
  - CASCADE: 연쇄적으로 삭제  
     ex) 사진들도 삭제 됨
  - SET NULL: null값으로 바꿈  
    ex) 사진의 주인 부분의 값은 null이 됨

<br>

##### nullable

---

- null값이 가능함

<br>

##### cascade

---

<br>

##### onUpdate

---

<br>

##### deferrable

---

<br>

##### primary

---

<br>

##### lazy

---

<br>

##### eager

---

<br>

##### persistence

---
