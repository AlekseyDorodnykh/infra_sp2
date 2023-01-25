## Описание
Проект Api_yamdb собирает отзывы пользователей на произведения. Сами произведения в YaMDb не хранятся, здесь нельзя посмотреть фильм или послушать музыку.

### Основные используемые технологии
1. Python 3.7 
2. Django 3.2
3. Django REST framework 
4. PostgreSQL 
5. Docker
6. GIT (https://github.com/git-guides)

### Документация и возможности API:
Для просмотра документиации к проекту подключен redoc. Для просмотра используется эндпойнт `redoc/`

### Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

```
git clone https://git@github.com:AlekseyDorodnykh/infra_sp2.git
```

```
cd infra
```

Развернуть контейнеры:


```
docker-compose up -d --build
```

В директории /infra создать файл .env с содержимым:


```
SECRET_KEY=default-key
DB_ENGINE=django.db.backends.postgresql 
DB_NAME=postgres # имя базы данных
POSTGRES_USER=postgres # логин для подключения к базе данных
POSTGRES_PASSWORD= # пароль для подключения к БД (установите свой)
DB_HOST=db # название сервиса (контейнера)
DB_PORT=5432 # порт для подключения к БД
```

Сделать миграции, суперпользователя и собрать статику:


```
docker-compose exec web python manage.py migrate
docker-compose exec web python manage.py createsuperuser
docker-compose exec web python manage.py collectstatic --no-input
```


Заполнить базу данными из копии:

```
docker-compose exec web python manage.py loaddata ../infra/fixtures.json 
```


### Автор проекта:
- [Дородных Алексей](https://github.com/AlekseyDorodnykh/)
