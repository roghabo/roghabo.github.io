---
title: "Javascript String관련 Method"
excerpt: ""

categories:
  - javascript

tags:
  - javascript
  - method

last_modified_at: 2021-01-14
---

##### trim

---

- 문자열 양 끝의 공백을 제거함
- Ex)
  ```javascript
  const value = "    Hi there!    ";
  console.log(value.trim());
  // output: "Hi there!"
  ```

<br>

##### toLowerCase

---

- 문자열을 소문자로 바꿈
- Ex)
  ```javascript
  const value = "Hi There!";
  console.log(value.toLowerCase());
  // output: "hi there!"
  ```

<br>

##### toUpperCase

---

- 문자열을 대문자로 바꿈
- Ex)
  ```javascript
  const value = "Hi There!";
  console.log(value.toUpperCase());
  // output: "HI THERE!"
  ```

<br>

##### replace

---

- 어떤 패턴이 일치하는 일부 또는 모든 부분이 교체된 새로운 문자열 반환(정규식 사용 가능)
- Ex)
  ```javascript
  const value = " Hi there! ";
  console.log(value.replace("", "-"));
  // output: "-Hi there! "
  console.log(value.replace(/ /g, "-"));
  // output: "-Hi-there!-"
  ```
