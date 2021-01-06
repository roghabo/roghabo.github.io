---
title: "React Router(typescript)"
excerpt: ""

categories:
  - react

tags:
  - react
  - typescript
  - router

last_modified_at: 2021-01-03
---

### React Router Dom

---

- typescript에서 react-router-dom을 사용하려면 별도의 package를 설치해야 함  
  `npm i @types/react-router-dom`

- Router사용 예시

  ```html
  import { BrowserRouter as Router, Route, Switch } from “react-router-dom”;

  <Router>
    <Switch>
      <Route path="/cafe">
        <Cafe />
      </Route>
      <Route path="/">
        <Home />
      </Route>
    </Switch>
  </Router>
  ```

  - Switch: 한 번에 하나의 Route만 Render하게 해줌
