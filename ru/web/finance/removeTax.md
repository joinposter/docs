## finance.removeTax: Удаление налога

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/finance.removeTax'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$tax = [
    'tax_id' => 3,
];

$data = sendRequest($url, 'post', $tax);
```

> Пример ответа:

```json
{  
  "response":true
}
```

Метод удаляет налог

### HTTP POST запрос

`https://joinposter.com/api/finance.removeTax`

### POST-параметры запроса finance.removeTax

Параметр | Описание
-------- | --------
tax_id | Id налога

### Параметры ответа finance.removeTax

Параметр | Описание
-------- | --------
response | true, если налог успешно удалён
