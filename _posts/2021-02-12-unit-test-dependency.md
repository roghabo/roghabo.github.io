---
title: "Unit Test Dependency문제 해결"
excerpt: "unit test dependency"

categories:
  - unit test

tags:
  - typescript
  - unit test

last_modified_at: 2021-02-12
---

- sevice에서 사용하는 repositories, services들을 제공해야 함

  - 실제가 아닌 mock repositry, mock service를 제공
  - Ex)

    ```typescript
    const mockRepository = {
      findOne: jest.fn(),
      save: jest.fn(),
      create: jest.fn(),
    };

    const module = await Test.createTestingModule({
      providers: [
        CoffeeService,
        {
          provide: getRepositoryToken(Coffee),
          useValue: mockRepository,
        },
        {
          provide: UserService,
          useValue: mockUserService,
        },
      ],
    }).compile();
    ```

    - fn() : mock 함수를 생성함
    - mock: 모조품
