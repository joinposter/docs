## clients.changeClientBonus: Изменение количества бонусов клиента

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/clients.changeClientBonus'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$bonus = [
  'client_id' => 7,
  'count'     => 10,
];

$data = sendRequest($url, 'post', $bonus);
```

> Пример ответа:

```json
{
  "response":30
}
```

Метод изменяет количество бонусов клиента. Используется только для клиентов с бонусной системой лояльности.

### HTTP запрос

`POST https://joinposter.com/api/clients.changeClientBonus`

### POST-параметры запроса clients.changeClientBonus

Параметр | Описание
-------- | --------
client_id | Id клиента
count | Количество бонусов, которые надо начислить клиенту. Если число положительное — начислить, если число отрицательное — списать.
block_webhook | Опциональный параметр, если true — в ответ не прийдет вебхук об измении данных этого клиента 

### Параметры ответа clients.changeClientBonus

Параметр | Описание
-------- | --------
response | Количество бонусов, которое стало у клиента после внесения изменений
