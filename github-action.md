# Github-Action

Github-Action은 CI/CD (Continuous Integeration, Continuous Develop) 플랫폼 입니다.

Github에 각종 이벤트에 작업을 수행할 수 있습니다.

## 예제

```yml
# 액션의 이름
name: action name

# 이 액션이 실행될 이벤트
on: [push]

# 실행할 작업들을 나열
jobs:
  # 실행할 작업의 이름
  job:
    # 실행 환경
    runs-on: ubuntu-latest
    # 실행 순서
    steps:
      # 순차적으로 실행하는 세부 작업의 이름 (Optional)
      - name: Check out repository code
      # 다른 action 로드 1
        uses: actions/checkout@v4
      - run: ls -al

      # 다른 action 로드 2
      - uses: actions/setup-node@v4
        with:
          node-version: 'latest'
      - run: npm i
      - run: npm run test
      - run: echo test done!
```

작업 수행중 에러가 발생하면 이후 작업들은 실행되지 않습니다.
