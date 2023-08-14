# taski-docker

Практика работы в Docker'ом и Nginx'ом. В ходе проекта удалось написать несколько образов для Docker'а и впоследствии развернуть их на удалённой Linux машине.

## Установка приложения

#### 1. Устанавливаем Docker

```
  https://www.docker.com/
```

#### 2. Клонируем репозиторий

```
  git@github.com:Anstane/taski-docker.git
```

#### 3. Запускаем Docker compose

```
  -Для установки из репозитория:

  docker compose -f docker-compose.production.yml up

  -Для установки с DockerHub:

  docker compose up
```

#### 4. Делаем миграции

```
  docker compose exec backend python manage.py makemigrations
  docker compose exec backend python manage.py migrate
```

#### 5. Собираем статику для backend`а

```
  docker compose exec backend python manage.py collectstatic
  docker compose exec backend cp -r ../app/static_backend/. ../var/html/
```
