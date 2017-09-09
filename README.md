# php-mysql-runner

[![](https://images.microbadger.com/badges/image/tsertkov/php-mysql-runner.svg)](https://microbadger.com/images/tsertkov/php-mysql-runner "Get your own image badge on microbadger.com")

> Task runner image with php and mysql client.

See example task scripts here: https://github.com/tsertkov/docker-compose-task-runner/blob/master/tasks

# Updating image

```
docker build -t tsertkov/php-mysql-runner
docker push tsertkov/php-mysql-runner
```

# Dockerfile

```
FROM php:latest

RUN apt-get update && apt-get install -y \
  mysql-client \
  less \
  vim \
  --no-install-recommends && rm -r /var/lib/apt/lists/* \
  && docker-php-ext-install pdo_mysql

CMD ["bash"]
```
