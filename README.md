# eat-front

## For Developer

```
npm install
```

### Build Docker Img

```
docker build -t vuejs/eat-front-docker .
```

### Start eat-front

```
docker run -it -p 9999:9999 --rm --name eat-front-docker-1 vuejs/eat-front-docker
```

### Run tests

```
npm run test
```

### Lints and fixes files

```
npm run lint
```

## env

## Server

[heroku](https://dashboard.heroku.com/apps)

Dev

- eat-front-dev

Stg

- eat-front-stg

## CI/CD

[Circleci](https://circleci.com/gh/KamabokoHouse/eat-front)
