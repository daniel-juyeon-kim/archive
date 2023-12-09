# Compose <!-- omit in toc -->

Compose는 다중 컨테이너를 실행할 수 있는 기능입니다.

명령어가 길거나 여러번 타이핑 해야하는 것을 Compose 파일 실행 한번에 수행 할 수 있습니다.

- [기존 도커 실행](#기존-도커-실행)
- [docker compose](#docker-compose)
  - [compose.yml 실행](#composeyml-실행)

## 기존 도커 실행

컨테이너의 실행은 아래와 같은 명령어를 타이핑하여 실행했습니다.

```docker
# Node.js 실행 명령어
docker run -dp 127.0.0.1:3000:3000 \
  -w /app -v "$(pwd):/app" \
  --network todo-app \
  -e MYSQL_HOST=mysql \
  -e MYSQL_USER=root \
  -e MYSQL_PASSWORD=secret \
  -e MYSQL_DB=todos \
  node:18-alpine \
  sh -c "yarn install && yarn run dev"

# MySQL 실행 명령어
docker run -d \
  --network todo-app --network-alias mysql \
  -v todo-mysql-data:/var/lib/mysql \
  -e MYSQL_ROOT_PASSWORD=secret \
  -e MYSQL_DATABASE=todos \
  mysql:8.0
```

실행할 명령어가 길고, 컨테이너가 많으면 일도 증가합니다. 또한 도커를 모르는 사람은 실행하기 쉽지 않습니다.

## docker compose

compose는 길고, 많은 명령을 한번에 처리할 수 있습니다.

실행할 명령어들을 하나의 파일에 담고, 실행하면 됩니다. 아래의 코드는 compose를 이용한 실행 명령 파일입니다.

```docker
services:

  # Node.js 실행 명령어
  app:
    image: node:18-alpine
    command: sh -c "yarn install && yarn run dev"
    ports:
      - 127.0.0.1:3000:3000
    working_dir: /app
    volumes:
      - ./:/app
    environment:
      MYSQL_HOST: mysql
      MYSQL_USER: root
      MYSQL_PASSWORD: secret
      MYSQL_DB: todos

  # MySQL 실행 명령어
  mysql:
    image: mysql:8.0
    volumes:
      - todo-mysql-data:/var/lib/mysql
    environment:
      MYSQL_ROOT_PASSWORD: secret
      MYSQL_DATABASE: todos

volumes:
  todo-mysql-data:
```

### compose.yml 실행

작성된 compose파일은 `docker compose up -d` 명령어를 이용하면 됩니다.
