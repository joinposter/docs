## incomingOrders.getTablesForReservation: Список столов для брони

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/incomingOrders.getTablesForReservation'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&date_reservation=15-07-2018 13:34'
 . '&duration=7200'
 . '&spot_id=1'
 . '&guests_count=3';

$data = sendRequest($url);
```

> Пример ответа:

```json
{
   "response":{
      "freeTables":[
         {
            "table_id":"85",
            "table_num":"2",
            "table_capacity":"3",
            "spot_id":"2",
            "hall_id":"5"
         },
         {
            "table_id":"98",
            "table_num":"9",
            "table_capacity":"3",
            "spot_id":"1",
            "hall_id":"3"
         },
         {
            "table_id":"91",
            "table_num":"2",
            "table_capacity":"4",
            "spot_id":"1",
            "hall_id":"3"
         },
         {
            "table_id":"94",
            "table_num":"5",
            "table_capacity":"5",
            "spot_id":"1",
            "hall_id":"3"
         }
      ]
   }
}
```

Метод возвращает доступные столы для бронирования

### HTTP GET запрос

`GET https://joinposter.com/api/incomingOrders.getTablesForReservation`

### GET-параметры запроса incomingOrders.getTablesForReservation

Параметр | Описание
-------- | --------
spot_id | Обязательный параметр, id заведения в которое придет онлайн-заказ
date_reservation | Обязательный параметр, дата начала брони в формате `Y-m-d H:i:s`
duration | Обязательный параметр, длительность брони в секундах. Должен быть не меньше 1800 секунд (пол часа).
guests_count | Количество гостей на которых бронируем столик


### Параметры ответа incomingOrders.getTablesForReservation

Параметр | Описание
-------- | --------
response | Объект ответа

Внутри параметра `response` лежит объект, внутри которого есть следующие параметры:

Параметр | Описание
-------- | --------
freeTables | Массив из объектов, содержит доступные столики для бронирования

Внутри параметра `freeTables` лежит объект, внутри которого есть следующие параметры:

Параметр | Описание
-------- | --------
table_id | Id стола
table_num | Номер стола
spot_id | Id заведения
hall_id | Id зала
table_capacity | Максимальное количество гостей за столом
