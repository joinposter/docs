## clients.changeClientPayedSum: Изменение общей суммы покупок клиента

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/clients.changeClientPayedSum'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$sum = [
  'client_id' => 50,
  'count'     => 20,
];

$data = sendRequest($url, 'post', $sum);
```

> Пример ответа:

```json
{
  "response":110
}
```

Метод изменяет общую сумму покупок клиента

### HTTP запрос

`POST https://joinposter.com/api/clients.changeClientPayedSum`

### POST-параметры запроса clients.changeClientPayedSum

Параметр | Описание
-------- | --------
client_id | Id клиента
count | Сумма покупок, которую надо начислить клиенту. Если число положительное — начислить, если число отрицательное — списать.
block_webhook | Опциональный параметр, если true — в ответ не прийдет вебхук об измении данных этого клиента

### Параметры ответа clients.changeClientPayedSum

Параметр | Описание
-------- | --------
response | Общая сумма покупок, которая стала у клиента после внесения изменений
