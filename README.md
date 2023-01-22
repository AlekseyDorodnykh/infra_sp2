# api_yamdb
api_yamdb

## Описание
Api_yamdb - проект, в котором пользователи могут делиться своими отзывами о произведениях при помощи API.

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
