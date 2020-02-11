## settings.changeSettings: Изменение свойств настроек клиентского аккаунта

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/settings.changeSettings'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$settings = [
    'uses_taxes'              => 1,
    'uses_cash_shifts'        => 0,
    'uses_fiscality'          => 0,
    'print_fiscal_by_default' => 0,
    'timezones'               => 'Europe/Moscow',
];

$data = sendRequest($url, 'post', $settings);
```

> Пример ответа:

```json
{  
  "response":true
}
```

Метод изменяет свойства настроек клиентского аккаунта

### HTTP POST запрос

`https://joinposter.com/api/settings.changeSettings`

### POST-параметры запроса settings.changeSettings

Параметр | Описание
-------- | --------
uses_taxes | Признак, использовать ли налоги: 0 — не использовать, 1 — использовать. По умолчанию не передаётся.
uses_cash_shifts | Признак, использовать ли кассовые смены: 0 — не использовать, 1 — использовать. По умолчанию не передаётся.
uses_fiscality | Признак, использовать ли фискализацию: 0 — не использовать, 1 — использовать. По умолчанию не передаётся.
print_fiscal_by_default | Признак, печатать ли фискальный чек по умолчанию: 0 — не печатать, 1 — печатать. По умолчанию не передаётся.
timezones | Часовой пояс. По умолчанию не передаётся.

### Параметры ответа settings.changeSettings

Параметр | Описание
-------- | --------
response | true, если свойства настроек клиентского аккаунта успешно изменены
