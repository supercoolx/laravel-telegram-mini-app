# Install Guide

## Preinstallation.

- php
- mysql
- composer

Check installation status.
``` console
$ php --version
PHP 8.2.12 (cli) (built: Oct 24 2023 21:15:15) (ZTS Visual C++ 2019 x64)
Copyright (c) The PHP Group
Zend Engine v4.2.12, Copyright (c) Zend Technologies
```
``` console
$ mysqld --version
C:\Program Files\MySQL\MySQL Server 8.0\bin\mysqld.exe  Ver 8.0.39 for Win64 on x86_64 (MySQL Community Server - GPL)
```
``` console
$ composer --version
Composer version 2.7.9 2024-09-04 14:43:28
PHP version 8.2.12 (C:\xampp\php\php.exe)
Run the "diagnose" command to get more detailed diagnostics output.
```

## Config .env

- Copy `.env.example ` to `.env`.

- Config your mysql database.
``` javascript
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=laravel
DB_USERNAME=root
DB_PASSWORD=
```

- Config your telegram bot token.

You can get bot token from [@BotFather](https://t.me/BotFather).

``` javascript
TELEGRAM_TOKEN=
```

- Config your JWT token.
``` javascript
JWT_SECRET=
```

## Install dependencies.
``` console
$ composer install
```

## Migrate database

``` console
$ php artisan migrate
```

## Change bot link

- In `/routes/telegram.php` file, change domain to your front-end.
``` php
$webAppUrl = "https://nuxt-telegram-mini-app.vercel.app/loading?user_id={$telegramUser->id}&token={$token}";
```
``` php
$webAppUrl = "https://nuxt-telegram-mini-app.vercel.app/?user_id={$telegramUser->id}&token={$token}";
```

## Run project

- Run backend api server
``` console
$ php artisan serve
```

- Run telegram bot
``` console
$ php artisan nutgram:run
```
