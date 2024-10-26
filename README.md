![workflow_status]
(https://github.com/emitka90/kittygram_final/actions/workflows/main.yml/badge.svg)

# __Kittygram__

Социальная сеть для обмена фотографиями любимых питомцев.

## Для кого этот проект

Этот проект объединяет всех неравнодушных владельцев домашних питомцев.

## Стек использованных технологий

- *Python 3.9*
- *Django 3.2.3*
- *Django REST framework 3.12.4*
- *JavaScript*
- *Nginx*
- *Docker compose*

## Запуск проекта

Клонируем репозиторий:

git@github.com:Emitka90/kittygram_final.git

Запускаем Docker Compose:

'''sudo docker compose -f docker-compose.production.yml up -d'''

Выполняем миграции, собераем статические файлы бэкенда и копируем их в /backend_static/static/:

'''sudo docker compose -f docker-compose.production.yml exec backend python manage.py migrate'''
'''sudo docker compose -f docker-compose.production.yml exec backend python manage.py collectstatic'''
'''sudo docker compose -f docker-compose.production.yml exec backend cp -r /app/collected_static/. /backend_static/static/'''

## Пример заполнения файла __.env__

'''POSTGRES_DB=kittygram
POSTGRES_USER=kittygram_user
POSTGRES_PASSWORD=kittygram_password
DB_NAME=kittygram
DB_HOST=db
DEBUG=False
SECRET_KEY=django_secret_key_example'''
