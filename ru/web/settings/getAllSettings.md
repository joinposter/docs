## settings.getAllSettings: Настройки аккаунта

>  Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/settings.getAllSettings'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);
```

> Пример ответа:

```json
{
    "response": {
        "COMPANY_ID": "demo",
        "FIZ_ADRESS_CITY": "joinposter.com",
        "FIZ_ADRESS_PHONE": "74993466863",
        "uses_tables": 1,
        "uses_cash_shifts": 1,
        "uses_taxes": 1,
        "uses_multiprice": 0,
        "tip_amount": 10,
        "uses_bookkeeping": 1,
        "uses_ipay": 0,
        "uses_manufacturing": 0,
        "uses_quick_waiter": 0,
        "company_name": "Демо-версия Poster",
        "company_type": 1,
        "timezones": "Europe/Kiev",
        "logo": "/upload/pos_cdb_4/icon.png",
        "lang": "ru",
        "pos_phone": "74993466863",
        "analytics_plus_time": 0,
        "uses_fiscality": 0,
        "print_fiscal_by_default": 0,
        "currency": {
            "currency_id": 1,
            "currency_name": "Гривна",
            "currency_code": "грн.",
            "currency_symbol": "₴",
            "currency_code_iso": "UAH"
        },
        "email": "root@joinposter.com",
        "name": "Demo"
    }
}
```

Метод возвращает данные по настройкам аккаунта

### HTTP GET запрос

`https://joinposter.com/api/settings.getAllSettings`

### Параметры ответа settings.getAllSettings

Параметр | Описание
-------- | --------
COMPANY_ID | Название аккаунта
FIZ_ADRESS_CITY | Адрес заведения
FIZ_ADRESS_PHONE | Телефон заведения
uses_tables | Признак используется ли карта столов: 0 — не используется, 1 — используется
uses_cash_shifts | Признак, используются ли кассовые смены: 0 — не используются, 1 — используются 
uses_taxes | Признак, используются ли налоги: 0 — не используются, 1 — используются 
uses_multiprice | Признак, используются ли разные цены в разных заведениях: 0 — не используются, 1 — используются 
tip_amount | Процент за обслуживание
uses_bookkeeping | Признак, используется ли бухгалтерия: 0 — не используется, 1 — используется 
uses_ipay | Признак, принимается ли оплата через iPay: 0 — не принимается, 1 — принимается 
uses_manufacturing | Признак, используется ли производство: 0 — не используется, 1 — используется 
uses_quick_waiter | Признак, используется ли быстрая смена официанта: 0 — не используется, 1 — используется 
company_name | Название заведения
company_type | Тип заведения: 1 — кафе, 2 — магазин
timezones | Часовой пояс
logo | Ссылка на логотип аккаунта
lang | Язык в формате ISO 639. Украинский язык обозначается как `ua`.
pos_phone | Телефон владельца аккаунта
analytics_plus_time | Бизнес-время окончания работы заведения
uses_fiscality | Признак, используется ли фискализация: 0 — не используется, 1 — используется 
print_fiscal_by_default | Признак, печатаются ли фискальные чеки по умолчанию: 0 — не печатаются, 1 — печатаются 
email | Эл. почта владельца аккаунта
name | Имя владельца аккаунта
currency | Валюта аккаунта

Внутри элемента currency лежит массив, в каждом элементе которого есть следующие свойства:

Параметр | Описание
-------- | --------
currency_id | Id валюты в Poster
currency_name | Название валюты
currency_code | Код валюты на терминале
currency_symbol | Unicode символ валюты, для рубля, драма и маната приходит HTML который на терминале отобразиться как иконка валюты
currency_code_iso | Цифровой код валюты по стандарту ISO 4217
