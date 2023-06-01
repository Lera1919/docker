# Создание окружения для разработки Веб-приложения

> <br>
>
> Программа **Docker** должна быть установлена на компьютере
> <br>
> <br>

Установка и настройка докера




### 1 Установка Docker
- 1.1 Скачиваем установщик https://docs.docker.com/get-docker/
- 1.2 Проверяем включена ли виртуализация, если выключена нужно включить через биос (спросить google)
- 1.3 Запустить установщик и пройти все этапы 
- 1.4 Запустить докер и дождаться когда он запуститься

# 2 Настройка
- 2.1 Переименовываем файл с конфигами .env.example  в .env  В PROJECT_DIR  путь где хранятся исходники всех ваших проектов.
- 2.2 Стягиваем нужный проект в папку с конфига PROJECT_DIR
- 2.3 Добвляем конфиг nginx, который вам скинет ктото из бека, в папку /config/nginx/conf.d/ и проверить что бы в конвиге совпадал путь к проекту в нутри контейнера (/var/www/...)
- 2.4 Запуск docker-compose (сборник всех ваших контейнеров). Открыть консоль в попке где храниться файл docker-compose.yml и выполнить команду 
```
docker-compose up -d
```
- 2.5 Проверить запустились ли все контейнеры http://joxi.ru/l2ZZlNBc7pGBy2  не должно быть статуса exit
```
    docker ps
```
- 2.6 Заходим в нутрь контейнера php

```
docker exec -ti php74 bash
или
winpty docker exec -ti php74 bash
```
- 2.7 Запуск composer. Переходим в проект с помощю команды cd /var/www/(имя проекта)... в папке должен быть файл composer.json и запускаем команду
```
 composer install
```
- 2.8 Подключаемся к БД через шторм http://joxi.ru/5mdyv78S8bOdP2 и добавляем соеденение  http://joxi.ru/a2XLK3pi4Ro3b2 
```
логин postgres
пароль 12345 (который в конфиге .env docker-compose POSTGRES_PASSWORD)
```
- 2.9 создаем базу http://joxi.ru/4AkM8pbHkv7Zym  и http://joxi.ru/xAe7v1dfXondOm  имя пишем название проекта которое потом нужно будет указать в конфиге

- 2.10 В папке с проектом находим файл .env  (если его нет то копируем с .env.example)  и прописываем конфиги базы 
http://joxi.ru/8AnQp6vHy5Ql82  название базы которую создали ранее и пароль которые прописан в конфиге докера

- 2.11 В консоле там где запускали composer выполняем миграции
```
php artisan migrate
```
- 2.12 Прописываем hosts в файле C:\Windows\System32\drivers\etc\hosts
http://joxi.ru/YmEb9nEHMNog72  домен должен совпадать с тем который указан в конфиге nginx

- 2.13 Запускаем браузер открываем домен сайта и радуемся что все работает!!!


 
