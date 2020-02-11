## clients.createClients: Групповое создание клиентов

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/clients.createClients'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$client = [
    [
        'client_name'             => 'Попова Елена Андреевна',
        'client_sex'              => 2,
        'client_groups_id_client' => 7,
        'card_number'             => '0000000000222',
        'discount_per'            => 0,
        'phone'                   => '+380519911122',
        'email'                   => 'contact@joinposter.com',
        'birthday'                => '1986-11-23',
        'bonus'                   => 10,
        'total_payed_sum'         => 417000,
    ],
    [
        'client_name'             => 'Егоров Денис Александрович',
        'client_sex'              => 1,
        'client_groups_id_client' => 7,
        'card_number'             => '0000000000223',
        'discount_per'            => 0,
        'phone'                   => '+380519998877',
        'email'                   => 'dev@joinposter.com',
        'birthday'                => '1990-06-15',
        'bonus'                   => 10,
        'total_payed_sum'         => 570000,
    ]
];

$data = sendRequest($url, 'post', $client);
```

> Пример ответа:

```json
{
  "response":[7, 8]
}
```

Метод создаёт клиента несколько клиентов за один запрос

### HTTP запрос

`POST https://joinposter.com/api/clients.createClients`

### POST-параметры запроса clients.createClients

Параметр | Описание
-------- | --------
client_name | ФИО клиента
client_sex | Пол клиента: 0 — не указан, 1 — мужской, 2 — женский
client_groups_id_client | Id группы клиентов
card_number | Номер карты клиента
discount_per | Персональный процент скидки или бонсов. Будет использоваться, если больше, чем процент группы клиента.
phone | Телефон клиента, уникальный, в системе не может быть два клиента с одинаковым номером
email | Адрес электронной почты клиента
birthday | Дата рождения клиента, формат "Y-m-d"
city | Город клиента
country | Страна клиента
address | Адрес клиента
comment | Комментарий к учетной записи клиента
bonus | Текущий размер накопленных бонусов клиента
total_payed_sum | Общая сумма покупок в копейках

### Параметры ответа clients.createClients

Параметр | Описание
-------- | --------
response | Массив id добавленных клиентов
