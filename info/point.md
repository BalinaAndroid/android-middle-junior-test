# Точки на карте

* Для всех запросов требуется авторизация

### Запрос списка точек

* Отправить `GET` `point/list`
* Доступные параметры
    * `page` - страница
    * `creator_id` - id создателя
    * `name` - название точки
    * `min_lat` - минимальная широта
    * `max_lat` - максимальная широта
    * `min_lng` - минимальная долгота
    * `max_lng` - максимальная долгота
    * `from` - минимальное время создания
    * `to` - максимальное время создания
    * `sort` - сортировка
* Доступные сортировки. По умолчанию `NEW`
  * `NEW` - сначала новые
  * `OLD` - сначала старые
* В качестве ответа будет список
```json
{
  "list": [
    {
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
  ],
  "total": 1
}
```

### Создание точки

* Отправить `POST` `point/create`
```json
{
  "name": "NAME",
  "description": "DESCRIPTION",
  "lat": 0.0,
  "lng": 0.0,
  "photos": [
    {
      "big_id": "01a190f80b2f7f02bd63c7da3a8435ad",
      "small_id": "01a190f80b2f7f02bd63c7da3a8435ad"
    }
  ]
}
```
* Ответом будет `id` новой точки
```json
{
  "id": "01a1934bc8a671d199906dc1b77929b9"
}
```

# Обновление точки
* Отправить `PUT` `point/update/01a1934bc8a671d199906dc1b77929b9`
```json
{
  "name": "NAME",
  "description": "DESCRIPTION",
  "lat": 0.0,
  "lng": 0.0,
  "photos": [
    {
      "big_id": "01a190f80b2f7f02bd63c7da3a8435ad",
      "small_id": "01a190f80b2f7f02bd63c7da3a8435ad"
    }
  ]
}
```
* Ответом будет `id` точки
```json
{
  "id": "01a1934bc8a671d199906dc1b77929b9"
}
```

# Удаление точки
* Отправить `DELETE` `point/delete/01a1934bc8a671d199906dc1b77929b9`
* При успехе ответом будет
```json
{
  "status": 200
}
```