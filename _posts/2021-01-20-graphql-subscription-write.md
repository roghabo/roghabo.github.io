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

subscription작성

- return타입과 상관없이 실제로는 asyncIterator(triggerName:string) 를 리턴해야 함
  - triggers: 기다리는 이벤트를 말함

subscription에 반응하는 이벤트 생성

- 이벤트에 trigger를 publish
  - pubsub.publish(triggerName, payload: Object)
    - payload에는 key에는 resolver함수의 이름

@Mutation(returns => Boolean)
potatoReady() {
pubsub.publish('orderCoffee', {
takeCoffee: 'Take your coffee',
});
return true;
}

@Subscription(returns => String)
takeCoffee() {
return pubsub.asyncIterator('orderCoffee');
}

—————————————————————————————

subscription filtering

@Subscription(returns => String), {
filter: (payload, variables, context) => {
return true;
},
})

—————————————————————————————

resolve: 사용자가 받는 update알림의 형태를 바꿔주는 일을 함
resolve(payload, args, context, info)

@Subscription(returns => String, {

    filter: ({ readyPotato }, { potatoId }) => {

      return readyPotato === potatoId;

    },

    resolve: ({ readyPotato }) =>

      `Your potato with the id ${readyPotato} is ready!`,

})

pubsub은 db에서만 쓸 수 있는게 아님
db에 저장하지 않아도 메세지를 보낼 수 있음
