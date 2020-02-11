## access.getTablets: Список терминалов

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/access.getTablets'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);
```

> Пример ответа:

```json
{
  "response":[
    {
      "tablet_id":"1",
      "tablet_name":"Основной на Мадридской",
      "spot_id":"1"
    },
    {
      "tablet_id":"2",
      "tablet_name":"Бар на Мадридской",
      "spot_id":"1"
    },
    {
      "tablet_id":"3",
      "tablet_name":"Терминал на Римской",
      "spot_id":"2"
    }
  ]
}
```

Метод возвращает список терминалов

### HTTP GET запрос

`https://joinposter.com/api/access.getTablets`

### Параметры ответа access.getTablets

Параметр | Описание
-------- | --------
response | Массив объектов

Внутри параметра `response` лежит массив, в каждом элементе которого есть следующие параметры:

Параметр | Описание
-------- | --------
tablet_id | Id терминала
tablet_name | Название терминала
spot_id | Id заведения к которому относится терминал
