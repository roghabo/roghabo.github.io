---
title: "Expect 함수의 Method"
excerpt: "unit test expect"

categories:
  - unit test

tags:
  - typescript
  - unit test

last_modified_at: 2021-02-12
---

### Expect

---

- Value를 테스트하고 싶을 때 사용하는 함수
  <br>
  <br>

#### Expect Method

---

1. toHaveBeenCalledTimes(expected: number)
   - mock funtion이 몇 번 불렸는지 확인
   - Ex)<br>
     `expect(coffeeRepositroy.create).toHaveBeenCalledTimes(1)`
     <br><br>
2. toHaveBeenCalledWith()

   - mock funtion가 호출될 때 어떤 인수와 호출되는지 확인
   - Ex)<br>

     ```
     expect(coffeeRepositroy.create).toHaveBeenCalledWith(createAccountArgs)

     expect(coffeeRepositroy.create).toHaveBeenCalledWith(
         expect.any(String),
         expect.any(String)
     )
     ```

     <br><br>

3. toHaveBeenCalled()
   - mock funtion가 호출이 되었는지 확인
   - Ex)<br>
     `expect(coffeeRepositroy.create).toHaveBeenCalled()`
     <br><br>
4. toMathObject()
   - Javascript 개체가 개체의 속성 하위 집합과 일치하는지 확인하는데 사용
   - Ex)<br>
     `expect(result).toMatchObject({ ok: false, error: 'Already Done', });`
     <br><br>
5. toBeDefined()
   - 변수가 정의 되었는지 확인
   - Ex)<br>
     `expect(service).toBeDefined();`
     <br><br>
6. toEqual()
   - 두 object이 같은지 확인
   - Ex)<br>
     `expect(result).toEqual({ ok: false, error: 'Already Done', });`
     <br><br>
