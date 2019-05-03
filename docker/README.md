# rails

## Initialize

```
$ docker-compose run web rails new . --force --database=[mysql]
```

## Edit database.yml

config/database.yml
```yml
default: &default
  adapter: mysql2
  encoding: utf8
  pool: <%= ENV.fetch("RAILS_MAX_THREADS") { 5 } %>
  username: <%= ENV.fetch("DB_USER") %>
  password: <%= ENV.fetch("DB_PASSWORD") %>
  host: db
```

## Create DB

```
$ docker-compose run --rm web rake db:create
```

## Create Images

```
$ docker-compose build
```

## Run docker

```
$ docker-compose up -d
```