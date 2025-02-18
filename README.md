# Лабораторная работа №3
## Цель работы
* Познакомиться с основными принципами работы с базами данных в Laravel. Научиться создавать миграции, модели и сиды на основе веб-приложения To-Do App.
## №1. Подготовка к работе
* Создание базы данных: Создайте новую базу данных для вашего приложения todo_app.
![image](https://github.com/user-attachments/assets/88f7f0f7-87c9-4916-8608-671f42b034af)

![image](https://github.com/user-attachments/assets/bb24ce62-0f5f-4d28-8d38-8814b9f17019)


* Настройте переменные окружения в файле .env для подключения к базе данных: env DB_CONNECTION=ваша_бд (mysql, pgsql, sqlite) DB_HOST=127.0.0.1 DB_PORT=3306 DB_DATABASE=todo_app DB_USERNAME=ваш_пользователь DB_PASSWORD=ваш_пароль

![image](https://github.com/user-attachments/assets/40fc3b26-7a2b-4eee-a435-9e8805f5de59)

![image](https://github.com/user-attachments/assets/3cf3d272-66e5-4963-9003-4d550a7f128e)

## №2. Создание моделей и миграций
* Создайте модель Category — категория задачи.

![image](https://github.com/user-attachments/assets/12dc4618-dfd3-4056-85fd-600a9253cfff)

* Определение структуры таблицы category в миграции:

![image](https://github.com/user-attachments/assets/cf4175af-e5ad-416b-9b46-fab401e8459b)

![image](https://github.com/user-attachments/assets/4798b58c-0f0f-4a8d-bb10-ccabedc1b60c)

* Создайте модель Task — задача.

![image](https://github.com/user-attachments/assets/8bd3d8ea-84ff-4a91-8d48-ef4888dd0630)

* Определение структуры таблицы task в миграции:

![image](https://github.com/user-attachments/assets/6c1aaf09-98dd-4602-96ab-b98313d34334)

![image](https://github.com/user-attachments/assets/c0316e43-7fba-4073-982b-4a6a9f0a2ec8)

* Запустите миграцию для создания таблицы в базе данных: bash php artisan migrate

![image](https://github.com/user-attachments/assets/76554d48-c74a-4568-82cc-0ee27c2cc876)


