
# DockerBX

Минимальное окржение для работы с проектом на базе BitrixFramework (под PHP 8, MySQL 8, Nginx, Redis)


## Установка

Скачать исходное окружение с репозитория

```bash
  git clone https://github.com/resolution07/dockerbx.git
```
Создать файл с переменными среды на основе .env.example

Запустить окружение
```bash
  docker-compose up -d --build
```

## Работа
Сразу после запуска будут доступны точки входа
- Установка - http://localgost/bitrixsetup.php
- Восстановление - http://localgost/restroe.php


## Соединение с базой данных
Для соединения с базой данные в качестве хоста указываем **db**.
Имя пользователя, пароль и название базы данных будет соответствовать значениям из **.env**:
- DB_USERNAME
- DB_PASSWORD
- DB_DATABASE
