Usege

```shell script
$ git clone git@github.com:matozaki-toshinori/laravel_docker.git
$ cd laravel_docker
$ docker-compose up -d --build
$ docker-compose exec app composer create-project --prefer-dist "laravel/laravel=6.5.2" .
```