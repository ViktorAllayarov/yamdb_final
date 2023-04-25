## ЯндексПрактикум. Спринт 12 - "Docker"
---
## Особенности:

Стандартный учебный проект YaMDb с системой регистрации/авторизации, создание, редактирование и оценка контента.

---
## API YaMDb
✅ Ресурс **/auth**: аутентификация.    

✅Ресурс **/users**: пользователи.

✅Ресурс **/titles**: произведения, к которым пишут отзывы (определённый фильм, книга или песенка).

✅Ресурс **/categories**: категории (типы) произведений («Фильмы», «Книги», «Музыка»).

✅Ресурс **/genres**: жанры произведений. Одно произведение может быть привязано к нескольким жанрам.

✅Ресурс **/reviews**: отзывы на произведения. Отзыв привязан к определённому произведению.

✅Ресурс **/comments**: комментарии к отзывам. Комментарий привязан к определённому отзыву.

## Документация проекта:
```
http://127.0.0.1/redoc/
```

### Запуск проекта в dev-режиме:

- Клонируем репозиторий:

```bash
git clone git@github.com:ViktorAllayarov/infra_sp2.git .
```

- Запускаем docker-compose:

```
docker-compose up
```

- Далее выполняем по очереди команды:

```
docker-compose exec web python manage.py migrate
docker-compose exec web python manage.py collectstatic --no-input
docker-compose exec web python manage.py loaddata
```

## ⤵️ Примеры запросов:

 - /redoc/ - документация
 - /api/v1/titles/ - получение списка всех произведений
 - /api/v1/titles/{titles_id}/ - получение информации о произведении

## ⤵️ Пример env-файла:
```
DB_ENGINE=django.db.backends.postgresql # указываем, что работаем с postgresql
DB_NAME=postgres # имя базы данных
POSTGRES_USER=postgres # логин для подключения к базе данных
POSTGRES_PASSWORD=postgres # пароль для подключения к БД (установите свой)
DB_HOST=db # название сервиса (контейнера)
DB_PORT=5432 # порт для подключения к БД
SECRET_KEY=key
```

![example workflow](https://github.com/ViktorAllayarov/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg)

## ️ Автор - Аллаяров Виктор