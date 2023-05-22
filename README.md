# Проект YaMDb

Проект YaMDb собирает отзывы пользователей на произведения.
Произведения делятся на категории: «Книги», «Фильмы», «Музыка».
Список категорий может быть расширен администратором.

## Автор проекта

- [Артём Хрущёв](https://github.com/TeenCreek)

## Доступен следующий функционал:

- auth: аутентификация
- users: пользователи
- titles: произведения, к которым пишут отзывы
- categories: категории произведений
- genres: жанры произведений
- reviews: отзывы на произведения
- comments: комментарии к отзывам

## Используемые технологии:

- Python
- Django
- DRF
- JWT
- Joser
- Docker
- Gunicorn
- PostgreSQL
- Nginx

## Как запустить проект:

1. Клонировать репозиторий

   ```
   git clone git@github.com:TeenCreek/infra_sp2.git
   ```

2. Перейти в папку:

   ```
   cd infra
   ```

3. Развернуть контейнеры:

   ```
   docker-compose up
   ```

4. Сделать миграции, суперпользователя и собрать статику:

   ```
   docker-compose exec web python manage.py migrate
   docker-compose exec web python manage.py createsuperuser
   docker-compose exec web python manage.py collectstatic --no-input
   ```

5. Заполнить базу данными из копии:
   ```
   docker-compose exec web python manage.py loaddata ../infra/fixtures.json
   ```

## Примеры запросов к API

```
GET /api/v1/titles/ - получить список произведений

POST /api/v1/titles/ - добавить новое произведение

GET /api/v1/titles/1/reviews/ - получить отзыв к произведению
```

> Подробную документацию по запросам к API можно посмотреть по _[ссылке](http://127.0.0.1/redoc/)_ после запуска сервера с проектом.

![example workflow](https://github.com/TeenCreek/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg)

- Имя образа в DockerHub - rakk69/apiyamdb
- Ip сервера - 51.250.110.226
