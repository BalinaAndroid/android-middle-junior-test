# Комментарии
* Для всех запросов требуется авторизация
* Можно прикреплять к:
    * Пользователям
    * Точкам на карте
    * Другим комментариям

### Доступные типы сообщений `message`
* Текстовое сообщение
```json
{
  "type": "text",
  "text": "message"
}
```
* Изображение
```json
{
  "type": "image",
  "photo": {
    "big_id": "01a190f80b2f7f02bd63c7da3a8435ad",
    "small_id": "01a190f80b2f7f02bd63c7da3a8435ad"
  }
}
```
* Изображение с текстом
```json
{
  "type": "image_text",
  "text": "message",
  "photo": {
    "big_id": "01a190f80b2f7f02bd63c7da3a8435ad",
    "small_id": "01a190f80b2f7f02bd63c7da3a8435ad"
  }
}
```
* Список изображений
```json
{
  "type": "image_list",
  "photos": [
    {
      "big_id": "01a190f80b2f7f02bd63c7da3a8435ad",
      "small_id": "01a190f80b2f7f02bd63c7da3a8435ad"
    }
  ]
}
```
* Список изображений с текстом
```json
{
  "type": "image_text_list",
  "text": "message",
  "photos": [
    {
      "big_id": "01a190f80b2f7f02bd63c7da3a8435ad",
      "small_id": "01a190f80b2f7f02bd63c7da3a8435ad"
    }
  ]
}
```

### Получить список комментариев

* Отправить `GET` `comment/list`
* Доступные параметры:
    * `page` - номер страницы. Опционально.
    * `relation_id` - `id` источника прикрепления.
* Ответ
```json
{
  "list": [
    {
      "id": "01a193575b2e7e0c8bf04bc2b71f2245",
      "creator": {
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
      },
      "message": {
        "type": "text",
        "text": "message"
      },
      "created_at": "2026-10-31T19:02:18.158413",
      "updated_at": "2026-10-31T19:02:18.158423",
      "comment_count": 0
    }
  ],
  "total": 1
}
```

### Создание комментария

* Отправить `POST` `comment/create`
```json
{
  "relation_id": "01a193575b2e7e0c8bf04bc2b71f2245",
  "message": {
    "type": "text",
    "text": "message"
  }
}
```
* В качестве ответа будет `id` нового поста
```json
{
  "id": "01a1935701437e899fe3a04eab26d322"
}
```

### Обновление комментария

* Отправить `PUT` `comment/update/01a1935701437e899fe3a04eab26d322`
```json
{
  "relation_id": "01a193575b2e7e0c8bf04bc2b71f2245",
  "message": {
    "type": "text",
    "text": "message"
  }
}
```
* В качестве ответа будет `id` обновленного поста
```json
{
  "id": "01a1935701437e899fe3a04eab26d322"
}
```

### Удаление комментария
* Отправить `DELETE` `comment/delete/01a193575b2e7e0c8bf04bc2b71f2245`
* В качестве ответа будет
```json
{
  "status": 200
}
```