## spots.getTableHallTables: Список столов

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/spots.getTableHallTables'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&spot_id=1'
 . '&hall_id=3'
 . '&without_deleted=1';

$data = sendRequest($url);
```

> Пример ответа:

```json
{  
  "response":[  
    {  
      "table_id":"3",
      "table_num":"1",
      "table_title":"Возле барной стойки",
      "spot_id":"1",
      "table_shape":"square",
      "hall_id":"1",
      "table_x":"9",
      "table_y":"12",
      "table_height":"4",
      "table_width":"8",
      "is_deleted":"0",
      "status":"1"
    },
    {  
      "table_id":"4",
      "table_num":"2",
      "table_title":"Дальний",
      "spot_id":"1",
      "table_shape":"circle",
      "hall_id":"1",
      "table_x":"15",
      "table_y":"11",
      "table_height":"10",
      "table_width":"13",
      "is_deleted":"0",
      "status":"2"
    }
  ]
}
```

Метод возвращает список столов

### HTTP запрос

`GET https://joinposter.com/api/spots.getTableHallTables`

### GET-параметры запроса spots.getTableHallTables

Параметр | Описание
-------- | --------
spot_id | Id заведения, по умолчанию не передаётся
hall_id | Id зала, по умолчанию не передаётся
without_deleted | Признак, возвращать ли без удалённых столов: 0 — с удалёнными столами, 1 — без удалённых столов. По умолчанию принимает 0.

### Параметры ответа spots.getTableHallTables

Параметр | Описание
-------- | --------
response | Массив объектов

Внутри параметра `response` лежит массив, в каждом элементе которого есть следующие параметры:

Параметр | Описание
-------- | --------
table_id | Id стола
table_num | Номер стола
table_title | Название стола
spot_id | Id заведения
table_shape | Форма стола: square — прямоугольная, circle — с закруглёнными краями
hall_id | Id зала
table_x | Координаты стола по оси X
table_y | Координаты стола по оси Y
table_height | Высота стола 
table_width | Ширина стола
is_deleted | Признак, что стол удалён: 0 — не удалён, 1 — удалён
status | Признак, есть ли на столе открытые заказы: 1 — нету открытых заказов, 2 — есть открытые заказы
