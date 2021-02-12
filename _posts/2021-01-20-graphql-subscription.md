---
title: "GraphQL Subscription"
excerpt: "GraphQL Subscription and Pubsub"

categories:
  - graphql

tags:
  - graphql
  - subscription

last_modified_at: 2021-01-20
---

### Subscription

---

- resolver에서 변경 사항이나 업데이트를 수신할 수 있게 해줌
- 웹 소켓을 활성화해야 사용할 수 있음

  - 웹 소켓에는 request가 없고 connection이 있음
    - connection은 웹소켓이 클라이언트와 서버 간의 연결을 설정하려고 할 때 발생함
  - 웹소켓은 시작할 때만 토큰을 보내고 연결 유지
    cf) http에서는 매번 request를 할 때마다 token을 보냄

    ##### 설치

    ***

    - `npm i graphql-subscriptions`

    ##### Seting

    ***

    - 웹 소켓 활성화하기
    - app.module

    ```typescript
    GraphQLModule.forRoot({
      installSubscriptionHandlers: true,
    });
    ```

### PubSub

---

- public and subscribe
- app 내부에서 메세지를 교환할 수 있음
- PubSub instance는 전체 어플리케이션에서 하나여야 함
- pubsub는 서버에 단일 인스턴스로 여러 개의 연결로 확장하지 않는 경우에만 작동함
  즉, 동시에 여러개의 서버를 가지고 있는 경우에는 X
  cf) RedisPubSub
- Ex)

  ```typescript
  const pubsub = new Pubsub();

  @Global()
  @Module({
      providers: [
          {
              provide: PUB_SUB,
              useValue: pubsub,
          },
      ],
      exports: [PUB_SUB],
  })
  ```

  - PUB_SUB을 사용할 곳에
    `@Inject(PUB_SUB) private readonly pubSub: PubSub`
