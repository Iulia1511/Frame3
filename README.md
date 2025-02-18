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

* Создайте модель Tag — тег задачи.

![image](https://github.com/user-attachments/assets/d97268a0-490a-41ad-ba70-6d1f1ec2da3d)

* Определение структуры таблицы tag в миграции:

![image](https://github.com/user-attachments/assets/ccf51e4d-97e4-4ce7-a127-2a21c5cb95ae)

* Добавьте поле $fillable в модели Task, Category и Tag для массового заполнения данных.

![image](https://github.com/user-attachments/assets/3637e384-607b-41c5-903b-089a85a16a16)

![image](https://github.com/user-attachments/assets/2815dfe4-69da-4acf-8c82-2215ca3ec1ee)

## №3. Связь между таблицами

* Создайте миграцию для добавления поля category_id в таблицу task.

![image](https://github.com/user-attachments/assets/43e9fda0-1a88-4f5a-a940-f1740423df08)

* Определите структуру поля category_id и добавьте внешний ключ для связи с таблицей category.

![image](https://github.com/user-attachments/assets/2ee82934-0b7c-4087-894b-12684a02515f)

*  Обновление модели Task

![image](https://github.com/user-attachments/assets/0ed3c26a-3ee5-4acc-92c0-bce6ef850c19)

* Создайте промежуточную таблицу для связи многие ко многим между задачами и тегами:

![image](https://github.com/user-attachments/assets/0d74d520-d9ed-4576-b6ca-9f71b1a2348c)

* Определение соответствующей структуры таблицы в миграции.

![image](https://github.com/user-attachments/assets/fc8ef127-7702-4621-adfc-e60cb036fc75)

* Добавляем связь в Task.php:

![image](https://github.com/user-attachments/assets/b87c2f28-426c-44d7-82d7-0e1b3f6b18c3)

* Добавляем связь в Tag.php:

![image](https://github.com/user-attachments/assets/788f9a2d-f7a0-4616-9029-da2cd977684b)

* Запустите миграцию для создания таблицы в базе данных.

![image](https://github.com/user-attachments/assets/2a1f18fd-d8c5-4cc1-8dcc-a2b772fd7442)

## №4. Связи между моделями
* Добавьте отношения в модель Category (Категория может иметь много задач)

![image](https://github.com/user-attachments/assets/2d6d0106-cee3-4e19-abc5-f7886dc4414b)

* Добавьте отношения в модель Task

![image](https://github.com/user-attachments/assets/76a3c51f-007b-4019-a834-b84092c4c035)

* Добавьте отношения в модель Tag (Тег может быть прикреплен к многим задачам)

![image](https://github.com/user-attachments/assets/0da00212-7a3b-4915-8da8-dc2fa5c5a894)

## №5. Создание фабрик и сидов

* Создайте фабрику для модели Category:

![image](https://github.com/user-attachments/assets/eca3ffab-7ee8-4677-b099-c3a594738043)

* Определите структуру данных для генерации категорий.

![image](https://github.com/user-attachments/assets/4a56c8a9-1076-44cf-8964-65acf504b626)

* Создайте фабрику для модели Task.

![image](https://github.com/user-attachments/assets/1b97d8d0-0cd3-4af9-91d2-f5045fdec952)

* Создайте фабрику для модели Tag.

 ![image](https://github.com/user-attachments/assets/a26ccb06-8063-44d2-bd3e-c787062e5c51)

* Создайте сиды (seeders) для заполнения таблиц начальными данными для моделей: Category, Task, Tag.
#### Сидер для категории:

  ![image](https://github.com/user-attachments/assets/4199d8e7-102b-4620-8ece-e11b7917b067)

  ![image](https://github.com/user-attachments/assets/1fe80756-89e2-43db-aff0-3b240575ab06)

#### Сидер для задач 

![image](https://github.com/user-attachments/assets/179ab192-e449-4535-8143-1bcde8c18031)

![image](https://github.com/user-attachments/assets/4fdaee76-90e2-47b7-907c-c6d20025c2e0)

#### Сидер для тегов

![image](https://github.com/user-attachments/assets/16599d02-04cf-4537-b508-853841e3f37f)

![image](https://github.com/user-attachments/assets/c8afdbec-32c6-4486-b3b4-ee31b75aa395)

* Обновите файл DatabaseSeeder для запуска сидов и запустите их: bash php artisan db:seed

![image](https://github.com/user-attachments/assets/60d36b13-c062-4019-bd59-8db7fc752571)

![image](https://github.com/user-attachments/assets/61906e59-fed6-4d81-adf1-4aaecd55fe83)

## №6. Работа с контроллерами и представлениями
* Откройте контроллер TaskController (app/Http/Controllers/TaskController.php).
*Обновите метод index для получения списка задач из базы данны
