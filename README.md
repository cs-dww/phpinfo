# RUN phpinfo WITHOUT CONTAINERIZATION

```
git clone https://github.com/academiaonline-org/phpinfo
cd phpinfo
git checkout main
```
```
php -f src/index.php -S 0.0.0.0:8080
```
```
curl localhost:8080/src/index.php
```

# RUN phpinfo WITH CONTAINERS

```
git clone https://github.com/academiaonline-org/phpinfo
cd phpinfo
git checkout 2022-01
```
```
git pull
```
```
docker build -f Dockerfile -t phpinfo:test .
```
```
docker run -d --entrypoint php --name phpinfo -v $PWD/src/index.php:/src/index.php:ro phpinfo:test -f src/index.php -S 0.0.0.0:8080
```
```
curl localhost:8080/src/index.php
```

