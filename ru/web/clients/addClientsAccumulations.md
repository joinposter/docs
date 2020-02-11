## clients.addClientsAccumulations: Редактирование накоплений клиента по акциям

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/clients.addClientsAccumulations'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$accumulations = [
  'accumulation_product_id' => 1,
  'tr_product_id'           => 2125193,
  'promotion_id'            => 14,
  'client_id'               => 62,
  'product_id'              => 934,
  'modification_id'         => 0,
  'status'                  => 1,
  'num'                     => 1.0000000,
  'product_sum'             => 1476,
  'prize_product_id'        => "1",
  'date_add'                => "2018-05-03 13:25:16",
  'date_close'              => "2018-05-03 13:26:00",
];

$data = sendRequest($url, 'post', $accumulations);
```

> Пример ответа:

```json
{  
   "response":"1"
}
```
 
Метод изменяет накопления клиента по акциям

### HTTP POST запрос

`GET https://joinposter.com/api/clients.addClientsAccumulations`

### POST-параметры запроса clients.addClientsAccumulations

Параметр | Описание
-------- | --------
accumulation_product_id | Id накопления 
tr_product_id | Уникальный id товара в рамках всех транзакций
promotion_id | Id акции
client_id | Id клиента
product_id | Id товара
modification_id | Id модификации, если товар с модификациями, 0 — если нет модификации
status | Статус накопления: 1 — активное, 2 — закрыто, 3 — удалено
num | Количество товара который выдан
product_sum | Стоимость одного купленного товара
prize_product_id | Id бонусного товара
date_add | Дата начала накопления в формате `YYYY-MM-dd HH:mm:ss`
date_close | Дата окончания накопления в формате `YYYY-MM-dd HH:mm:ss`

### Параметры ответа clients.addClientsAccumulations

Параметр | Описание
-------- | --------
response | 1, если накопления добавлены
