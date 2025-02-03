# DockerLaravel
Репозиторий с настроенным для запуска в докере проектом

# Версии

<table>
    <tr>
        <td>Версия</td>
        <td>Ветка</td>
    </tr>
    <tr>
        <td>Laravel 10, php 8.1.1, rabbit</td>
        <td><a href="https://github.com/NikitinUser/DockerLaravel/tree/laravel-10">laravel-10</a></td>
    </tr>
    <tr>
        <td>Laravel 11, php 8.1.1, rabbit</td>
        <td><a href="https://github.com/NikitinUser/DockerLaravel/tree/laravel-11">laravel-11</a></td>
    </tr>
    <tr>
        <td>Laravel 11, php 8.2.1, rabbit, kafka</td>
        <td>laravel-11-kafka (current)</td>
    </tr>
</table>

# Настроены
1. nginx
2. pgsql
3. php + laravel 11
4. kafka
5. redis
6. cron

# Предустановлены:
1. Пакет для jwt авторизации tymon/jwt-auth (все настроено)
2. Пакет для свагер аннотаций zircote/swagger-php
3. Пакет vladimir-yuldashev/laravel-queue-rabbitmq
4. Пакет predis/predis

# Для запуска бэка:
1. cd backend
2. cp .env.example .env
3. sudo make up
4. make install
5. make migrate
6. make jwt-init
7. make user-management-role-init
8. php artisan app:set-admin {id_user} // опционально

# Swagger
    Для генерации Swagger по аннотациям используются библиотеки:
        - zircote/swagger-php
        - doctrine/annotations
    Для запуска генерации выполнить команду:
        - ./vendor/bin/openapi app -o openapi.yaml
