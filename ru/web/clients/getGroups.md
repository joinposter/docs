## clients.getGroups: Список групп клиентов

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/clients.getGroups'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);
```

> Пример ответа:

```json
{  
  "response":[  
    {  
      "client_groups_id":"2",
      "client_groups_name":"Скидка Выходной",
      "client_groups_discount":"15",
      "loyalty_type":"1",
      "birthday_bonus":"0",
      "count_groups_clients":"21",
      "use_ewallet":"0",
      "delete":"0"
    },
    {  
      "client_groups_id":"3",
      "client_groups_name":"Накопительная скидка",
      "client_groups_discount":"0",
      "loyalty_type":"1",
      "birthday_bonus":"0",
      "count_groups_clients":"8",
      "use_ewallet":"0",
      "delete":"0"
    }
  ]
}
```

Метод возвращает список групп клиентов

### HTTP запрос

`GET https://joinposter.com/api/clients.getGroups`

### Параметры ответа clients.getGroups

Параметр | Описание
-------- | --------
response | Массив объектов

Внутри параметра `response` лежит массив, в каждом элементе которого есть следующие параметры:

Параметр | Описание
-------- | --------
client_groups_id | Id группы клиентов
client_groups_name | Название группы клиентов
client_groups_discount | Процент группы. Если группа бонусная, то будет начислять бонусы на оплаченную сумму заказа. Если группа скидочная, то будет давать процент скидки на сумму заказа.
loyalty_type | Тип группы клиентов: 1 — бонусная, 2 — скидочная
birthday_bonus | Количество бонусов в копейках начисляемые в день рождения клиента. Используется только бонусными группами.
count_groups_clients | Количество клиентов, которые находятся в данной группе
use_ewallet | Признак могут ли клиенты группы иметь депозитный счет: 0 — не использовать, 1 — использовать
delete | Определяет удалена ли группа: 1 — удалена, 0 — нет
