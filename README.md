Простое REST API для управления задачами. Выполнено в рамках тестового задания на позицию Junior PHP Developer. 

**Стек технологий:** 
- PHP 8.2
- Laravel 12
- SQLite
- Laravel sail

**Возможности API:** 
- Получение списка задач
- Получение одной задачи по ID
- Создание новой задачи
- Обновление задачи
- Удаление задачи

**Каждая задача содержит:** 
- название(title)
- описание(description)
- статус(status)

**Установка и запуск:** 
1. Клонирование репозитория
   
git clone https://github.com/sunsungiee/todo-api.git

    cd todo-api

**2. Создание .env** 

    cp .env.example .env

*Т.к. проект использует SQLite, нужно создать файл базы данных*

    touch database/database.sqlite

**3. Запуск через Laravel Sail** 

    composer install
    
    ./vendor/bin/sail up -d

**4. Генерация ключа** 

    ./vendor/bin/sail artisan key:generate

**5. Миграция** 

    ./vendor/bin/sail artisan migrate 

**API доступно по адресу:** 
http://localhost/api/tasks


**API эндпоинты** 
- Получить все задачи
  - GET /api/tasks

- Получить задачу по ID
    - GET /api/tasks/{id}

- Создать задачу
    - POST /api/tasks

- Обновить задачу
    - PUT /api/tasks/{id}

- Удалить задачу
    - DELETE /api/tasks/{id}
 
<img width="401" height="240" alt="изображение" src="https://github.com/user-attachments/assets/ce5547aa-cb0b-45f6-b9f6-fa8daf3e2edb" />


**Реализована пагинация по страницам каждые 15 записей (http://localhost/api/tasks?page=1)** 


**Для тестирования были созданы TaskSeeder и TaskFactory.** 

    ./vendor/bin/sail artisan db:seed --class=TaskSeeder


Тестирование проводилось вручную через curl.
