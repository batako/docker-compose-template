# rails

## Initialize

```
$ docker-compose run --rm web rails new . --force --database=[postgresql, mysql]
```

## Edit database.yml

config/database.yml
```yml
default: &default
+  username: <%= ENV.fetch("DB_USER") %>
+  password: <%= ENV.fetch("DB_PASSWORD") %>
+  host: db
```

## Create images

```
$ docker-compose build
```

## Delete unnecessary image

```
$ docker rmi $(docker images -f dangling=true -q)
```

## Create db

```
$ docker-compose run --rm web rake db:create
```

## Run docker

```
$ docker-compose up -d
```