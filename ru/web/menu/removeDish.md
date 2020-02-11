## menu.removeDish: Удаление тех. карты

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/menu.removeDish'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$dish = [
    'dish_id' => 925,
];

$data = sendRequest($url, 'post', $dish);
```

> Пример ответа:

```json
{  
  "response":true
}
```

Метод удаляет тех. карту

### HTTP запрос

`GET https://joinposter.com/api/menu.removeDish`

### POST-параметры запроса menu.removeDish

Параметр | Описание
-------- | --------
dish_id | Id тех. карты

### Параметры ответа menu.removeDish

Параметр | Описание
-------- | --------
response | true, если тех. карта успешно удалена
