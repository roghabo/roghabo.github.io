---
title: "Nestjs에서 Postgresql, TypeORM 사용하기"
excerpt: ""

categories:
  - nestjs

tags:
  - nestjs
  - typeorm
  - postgresql

last_modified_at: 2020-12-24
---

### Postgresql 사용하기

---

1. postgre앱 설치
2. postico 설치
3. postico에서 데이터베이스 생성
4. 데이터베이스 비밀번호 설정  
   4-1. postgre앱에서 설정할 데이터베이스 더블클릭  
   4-2. 쿼리 작성  
   `ALTER USER 유저명 WITH PASSWORD '비밀번호'`
   <br><br>

### TypeOrm을 사용하여 Nest JS와 database연결

---

1. 패키지 설치  
   `npm i @nestjs/typeorm typeorm pg`
   (마지막 pg는 postgresql이라는 뜻)

2. app.module.ts에 TypeOrmModule 설정

   ```javascript
   import { TypeOrmModule } from '@nestjs/typeorm'
   @Module({
     TypeOrmModule.forRoot({
       type: 'postgres',
       host: 'localhost',
       port: 5432,
       username: 'username',
       password: 'test',
       database: 'database',
       synchronize: true,
       logging: true,
     })
   })
   ```

   - synchronize: typeOrm이 Entity를 찾고 알아서 migration해줌
   - logging: 데이터베이스에서 무슨 일이 일어나는지 콘솔에 표시함
