---
title: "React Hook Form"
excerpt: ""

categories:
  - hook

tags:
  - react
  - hook

last_modified_at: 2021-01-03
---

### React Hook Form

---

- react hook으로 form을 쉽게 만들 수 있도록 도와줌
- 설치  
  `npm i react-hook-form`

- 기본 예제

  ```typescript
  import React from "react";
  import { useForm } from "react-hook-form";

  Interface Inputs = {
    example: string,
    exampleRequired: string,
  };

  export default function App() {
    const { register, handleSubmit, watch, errors } = useForm<Inputs>();
    const onSubmit = data => console.log(data);

    console.log(watch("example"))

    return (
      <form onSubmit={handleSubmit(onSubmit)}>

        <input name="example" defaultValue="test" ref={register} />
        <input name="exampleRequired" ref={register({ required: true })} />

        {errors.exampleRequired && <span>This field is required</span>}

        <input type="submit" />
      </form>
    );
  }
  ```

  - input태그에 name을 설정해 주어야 useForm이 찾을 수 있음
  - handleSubmit(): form이 valid할 때 form 데이터를 넘겨줌
  - watch(): 실시간 변화를 감지함

  > React Hook Form 공식문서
