## menu.updateWorkshop: Изменение свойств цеха

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/menu.updateWorkshop'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$workshop = [
    'workshop_id'  => 5,
    'product_name' => 'Суши',
];

$data = sendRequest($url, 'post', $workshop);
```

> Пример ответа:

```json
{  
  "response":5
}
```

Метод изменяет свойства цеха

### HTTP запрос

`GET https://joinposter.com/api/menu.updateWorkshop`

### POST-параметры запроса menu.updateWorkshop

Параметр | Описание
-------- | --------
workshop_id | Id цеха
workshop_name | Название цеха

### Параметры ответа menu.updateWorkshop

Параметр | Описание
-------- | --------
response | Id изменённого цеха
