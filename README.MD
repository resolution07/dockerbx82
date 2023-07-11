
# DockerBX82

Минимальное окржение для работы с проектом на базе BitrixFramework (под PHP 8.2, MySQL 8, Nginx, Redis)


## Установка

Скачать исходное окружение с репозитория

```bash
  git clone https://github.com/resolution07/dockerbx82.git
```
Создать файл с переменными среды на основе .env.example
**Добавить в корень папку app**

Запустить окружение
```bash
  docker-compose up -d --build
```

## Соединение с базой данных
Для соединения с базой данные в качестве хоста указываем **db**.
Имя пользователя, пароль и название базы данных будет соответствовать значениям из **.env**:
- DB_USERNAME
- DB_PASSWORD
- DB_DATABASE
