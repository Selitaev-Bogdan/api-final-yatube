# API для Yatube

## Описание проекта
API для социальной сети Yatube. Проект разработан в рамках учебного курса Яндекс Практикум.

### Функциональность:
- Публикация постов с возможностью добавления изображений
- Комментирование постов
- Подписка на авторов
- Группы (сообщества) для постов
- JWT-аутентификация
- Пагинация и поиск

## Технологии
- Python 3.12
- Django 3.2
- Django REST Framework 3.12
- Simple JWT 4.7
- Djoser 2.1
- SQLite (для разработки)

## Установка и запуск

### 1. Клонирование репозитория
git clone https://github.com/Selitaev-Bogdan/api-final-yatube.git
cd api-final-yatube

### 2. Создание виртуального окружения
python -m venv venv

### 3. Активация виртуального окружения
Windows (Git Bash):
source venv/Scripts/activate

Linux/Mac:
source venv/bin/activate

### 4. Установка зависимостей
pip install -r requirements.txt

### 5. Выполнение миграций
python manage.py migrate

### 6. Создание суперпользователя
python manage.py createsuperuser

### 7. Запуск сервера разработки
python manage.py runserver

## Документация API
После запуска сервера документация доступна по адресу:
http://127.0.0.1:8000/redoc/

## Примеры запросов к API

### Получение списка постов
GET /api/v1/posts/

### Создание нового поста
POST /api/v1/posts/
Authorization: Bearer <ваш_JWT_токен>
{
    "text": "Текст нового поста"
}

### Получение JWT токена
POST /api/v1/jwt/create/
{
    "username": "your_username",
    "password": "your_password"
}

### Подписка на пользователя
POST /api/v1/follow/
Authorization: Bearer <ваш_JWT_токен>
{
    "following": "username_автора"
}

## Эндпоинты API
- GET /api/v1/posts/ - список постов
- POST /api/v1/posts/ - создание поста
- GET /api/v1/posts/{id}/ - получение поста
- PUT /api/v1/posts/{id}/ - обновление поста
- PATCH /api/v1/posts/{id}/ - частичное обновление
- DELETE /api/v1/posts/{id}/ - удаление поста
- GET /api/v1/groups/ - список групп
- GET /api/v1/groups/{id}/ - информация о группе
- GET /api/v1/posts/{post_id}/comments/ - комментарии к посту
- POST /api/v1/posts/{post_id}/comments/ - добавление комментария
- GET /api/v1/follow/ - подписки пользователя
- POST /api/v1/follow/ - подписка на автора

## Права доступа
- Анонимные пользователи - только чтение
- Авторизованные пользователи - создание постов и комментариев, подписки
- Авторы контента - полный доступ к своим постам и комментариям

## Автор
Селитаев Богдан
