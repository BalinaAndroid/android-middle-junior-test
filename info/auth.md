# Регистрация / Вход 

### Проверка логина

* Отправить `GET` запрос `auth/login/check`
* Параметры:
*  * `login` - строка, требуемый.


### Регистрация

* Отправить `POST` запрос `auth/register` 
* В body передать логин и пароль 
```json
{
    "login": "login",
    "password": "password"
}
```
* При успехе в качестве ответа будут выданы `access_token` и `refresh_token` 
```json
{
  "access_token": "*.*.*",
  "refresh_token": "*.*.*"
}
```

### Вход

* Отправить `POST` запрос `auth/login`
* В body передать логин и пароль
```json
{
    "login": "login",
    "password": "password"
}
```
* При успехе в качестве ответа будут выданы `access_token` и `refresh_token`
```json
{
  "access_token": "*.*.*",
  "refresh_token": "*.*.*"
}
```

### Проверка токена

* Добавить `access_token` в `header` в виде `Authorization: Bearer access_token`  
* Сделать `GET` запрос `auth/protected`
* При успехе ответ будет вида
```json
{
  "status": 200
}
```

### Обновление токена
* Отправить `POST` запрос `auth/refresh`
* В body передать `refresh_token`
```json
{
  "refresh_token": "refresh_token"
}
```
* При успехе в качестве ответа будут обновлены `access_token` и `refresh_token`
```json
{
  "access_token": "*.*.*",
  "refresh_token": "*.*.*"
}
```