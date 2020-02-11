## clients.updateGroup: Изменение свойств группы клиентов

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/clients.updateGroup'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$group = [
  'client_groups_id'       => 5,
  'client_groups_name'     => 'Постоянный посетитель',
  'loyalty_type'           => 1,
  'client_groups_discount' => 10,
  'birthday_bonus'         => 50.00,
];

$data = sendRequest($url, 'post', $group);
```

> Пример ответа:

```json
{
  "response":6
}
```

Метод изменяет свойства группы клиентов

### HTTP запрос

`POST https://joinposter.com/api/clients.updateGroup`

### POST-параметры запроса clients.updateGroup

Параметр | Описание
-------- | --------
client_groups_id | Id группы клиентов
client_groups_name | Название группы клиентов
loyalty_type | Тип группы клиентов: 1 — бонусная, 2 — скидочная
client_groups_discount | Процент группы. Если группа бонусная — 1, то будет начислять бонусы на оплаченную сумму заказа. Если группа скидочная — 2, то будет давать процент скидки на сумму заказа.
birthday_bonus | Количество бонусов в копейках начисляемые в день рождения клиента. Используется только бонусными группами.
use_ewallet | Признак для использования депозитных счетов в группе клиентов: 0 — не использовать, 1 — использовать

### Параметры ответа clients.updateGroup

Параметр | Описание
-------- | --------
response | id измененной группы клиентов
