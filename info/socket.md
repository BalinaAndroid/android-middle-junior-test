# Сокет

### Подключение
* Подключаться по адресу `wss://uotest.duckdns.org/channel`
* Для подключения передавать в header `Authorization: Bearer access_token`
* Сокет сообщает о произошедших изменениях:
    * Обновление пользователя
    * Создание, обновление, удаление точки
    * Создание, обновление, удаление комментария
* Данные приходят в виде `json`


### Доступные ответы
* Обновление пользователя
```json
{
  "type": "user_updated",
  "data": {
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
}
```
* Создание, обновление точки
```json
{
  "type": "point_updated",
  "data": {
    "id": "01a1934bc8a671d199906dc1b77929b9",
    "name": "NAME",
    "description": "DESCRIPTION",
    "lat": 0.0,
    "lng": 0.0,
    "created_at": "2026-10-31T18:49:39.750486",
    "updated_at": "2026-10-31T18:49:39.750486",
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
    "photos": [
      {
        "big_id": "01a190f80b2f7f02bd63c7da3a8435ad",
        "small_id": "01a190f80b2f7f02bd63c7da3a8435ad"
      }
    ],
    "comment_count": 0
  }
}
```
* Удаление точки
```json
{
  "type": "point_deleted",
  "data": {
    "id": "01a1934bc8a671d199906dc1b77929b9"
  }
}
```
* Создание, обновление комментария
```json
{
  "type": "comment_updated",
  "data": {
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
}
```
* Удаление комментария
```json
{
  "type": "comment_deleted",
  "data": {
    "id": "01a1934bc8a671d199906dc1b77929b9"
  }
}
```