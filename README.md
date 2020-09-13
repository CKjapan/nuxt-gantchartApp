# 手順

## Start

bash

```bash
touch Dockerfile docker-compose.yml
```

Dockerfile

```yaml
FROM node:12.16.1
WORKDIR /usr/src/app
RUN yarn global add @vue/cli

ENV HOST 0.0.0.0
ENV PORT 3000
```

docker-compose.yml

```yaml
version: "3"
services:
  app:
    build: .
    container_name: gant
    ports:
      - "3000:3000"
    volumes:
      - .:/usr/src/app
    working_dir: /usr/src/app
    stdin_open: true
    tty: true
```

bash

```bash
docker-compose build
docker-compose up -d
docker-compose exec app /bin/bash
yarn create nuxt-app frontend
cd frontend
$  yarn dev
```

## Link

[Vue-Ganttastic](https://infectoone.github.io/vue-ganttastic-homepage/#/example)
