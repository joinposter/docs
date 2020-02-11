## clients.updateClient: Изменение свойств клиента

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/clients.updateClient'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$client = [
  'client_id'               => 50,
  'client_name'             => 'Попова Елена Андреевна',
  'client_sex'              => 2,
  'client_groups_id_client' => 7,
  'card_number'             => '0000000000222',
  'discount_per'            => 0,
  'phone'                   => '+380 50 22-11-111',
  'email'                   => 'contact@joinposter.com',
  'birthday'                => '1986-11-23',
  'bonus'                   => 10,
  'total_payed_sum'         => 417000,
];

$data = sendRequest($url, 'post', $client);
```

> Пример ответа:

```json
{
  "response":4082
}
```

Метод изменяет свойства клиента

### HTTP запрос

`POST https://joinposter.com/api/clients.updateClient`

### POST-параметры запроса clients.updateClient

Параметр | Описание
-------- | --------
client_id | Id клиента
client_name | ФИО клиента
client_sex | Пол клиента: 0 — не указан, 1 — мужской, 2 — женский
client_groups_id_client | Id группы клиентов
card_number | Номер карты клиента
discount_per | Персональный процент скидки или бонсов. Будет использоваться, если будет больше, чем процент группы клиента.
phone | Телефон клиента, уникальный, в системе не может быть два клиента с одинаковым номером
email | Адрес электронной почты клиента
birthday | Дата рождения клиента, формат "Y-m-d"
city | Город клиента
country | Страна клиента
address | Адрес клиента
comment | Комментарий к учетной записи клиента
bonus | Текущий размер накопленных бонусов клиента
total_payed_sum | Общая сумма покупок в копейках

### Параметры ответа clients.updateClient

Параметр | Описание
-------- | --------
response | Id измененного клиента
