## franchise.getSpots: Список заведений во франчайзи по всей франшизе

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/franchise.getSpots'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);

```

> Пример ответа:

```json
{  
   "response":{  
      "demo-franchisee":[  
         {  
            "spot_id":1,
            "name":"Демо франчайзи",
            "address":""
         },
         {  
            "spot_id":2,
            "name":"Демо франчайзи2",
            "address":""
         }
      ]
   }
}
```

Метод возвращает список заведений во франчайзи по всей франшизе

### HTTP GET запрос

`GET https://joinposter.com/api/franchise.getSpots`


### Параметры ответа franchise.getSpots

Параметр | Описание
-------- | --------
response | Массив объектов

Внутри параметра `response` лежит список, где ключ — название франчайзи, а значение массив со списком заведений этой франчайзи. 
Каждый объект массива содержит следующие значения:

Параметр | Описание
-------- | --------
spot_id | Id заведения
spot_name | Название заведения
spot_adress | Адрес заведения

