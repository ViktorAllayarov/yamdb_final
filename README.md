## ЯндексПрактикум. Спринт 12 - "Docker"
---

![ЯндексПрактикум. Спринт 12.](https://github.com/ViktorAllayarov/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg)

## Особенности:

Стандартный учебный проект YaMDb с системой регистрации/авторизации, создание, редактирование и оценка контента.

Проект доступен по адресу :

✅ Для доступа к API
http://158.160.31.116/api/v1/

✅ Админка
http://158.160.31.116/admin/ 

✅ Документация к проекту
http://158.160.31.116/redoc/

---
## Стек технологий
Python 3
Django 3.2
DRF (Django REST framework)
Django ORM
Docker
Docker Compose
Gunicorn
nginx
PostgreSQL

---
## API YaMDb
✅ Ресурс **/auth**: аутентификация.    

✅Ресурс **/users**: пользователи.

✅Ресурс **/titles**: произведения, к которым пишут отзывы (определённый фильм, книга или песенка).

✅Ресурс **/categories**: категории (типы) произведений («Фильмы», «Книги», «Музыка»).

✅Ресурс **/genres**: жанры произведений. Одно произведение может быть привязано к нескольким жанрам.

✅Ресурс **/reviews**: отзывы на произведения. Отзыв привязан к определённому произведению.

✅Ресурс **/comments**: комментарии к отзывам. Комментарий привязан к определённому отзыву.

### Запуск проекта в dev-режиме:

- Клонируем репозиторий:

```
git clone git@github.com:ViktorAllayarov/yamdb_final.git .
```

- Запускаем docker-compose:

```
docker-compose up --build
```

- Затем узнать id контейнера, для этого вводим

```
docker container ls
```

- Выбираем интересующий нас контейнер:

```
docker exec -it <CONTAINER ID> sh
```

- Далее выполняем по очереди команды:

```
python manage.py migrate
python manage.py collectstatic --no-input
python manage.py createsuperuser
```

- Далее загружаем фикстуры при необходимости

```
python manage.py loaddata fixtures.json
```

## ⤵️ Примеры запросов:

 - /redoc/ - документация
 - /api/v1/titles/ - получение списка всех произведений
 - /api/v1/titles/{titles_id}/ - получение информации о произведении

 ## Документация проекта:
```
http://127.0.0.1/redoc/
```
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

## ️ Автор - Аллаяров Виктор