---
title: "Unit Test 하기"
excerpt: "unit test"

categories:
  - unit test

tags:
  - typescript
  - unit test

last_modified_at: 2021-02-12
---

#### Test 만들기

---

- Ex)

  ```typescript
  describe('서비스이름', () => {
      describe('메소드 이름', () => {
          it('테스트 이름', async () => {
              expect(service).toBeDefined();
          }
      }
  }
  ```
