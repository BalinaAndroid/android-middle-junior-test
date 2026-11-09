# Пользователи
* Для всех запросов требуется авторизация

### Мой пользователь

* Запросить `GET` `user/my`
* В качестве ответа будет информация о пользователе

```json
{
  "id": "01a192798c6f7956bb73af8f3c337c87",
  "first_name": "first",
  "last_name": "last",
  "photos": [
    {
      "big_id": "01a190f80b2f7f02bd63c7da3a8435ad",
      "small_id": "01a190f80b2f7f02bd63c7da3a8435ad"
    }
  ],
  "comment_count": 0
}
```

### Другой пользователь

* Запросить `GET` `user/01a192798c6f7956bb73af8f3c337c87`
* В качестве ответа будет информация о пользователе
```json
{
  "id": "01a192798c6f7956bb73af8f3c337c87",
  "first_name": "first",
  "last_name": "last",
  "photos": [
    {
      "big_id": "01a190f80b2f7f02bd63c7da3a8435ad",
      "small_id": "01a190f80b2f7f02bd63c7da3a8435ad"
    }
  ],
  "comment_count": 0
}
```

### Обновление пользователя

* Отправить `PUT` `user/update`
* Прикрепить к запросу `body` необходимые данные
```json
{
    "first_name": "first",
    "last_name": "last",
    "photos": [
        {
            "big_id": "01a190f80b2f7f02bd63c7da3a8435ad",
            "small_id": "01a190f80b2f7f02bd63c7da3a8435ad"
        }
    ]
}
```

