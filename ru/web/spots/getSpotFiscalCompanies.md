## spots.getSpotFiscalCompanies: Информация о фискальных компаниях всех заведений

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/spots.getSpotFiscalCompanies'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = PosterAPI::sendRequest($url);
```

> Пример ответа:

```json

[
  {
    "spot_id": 1,
    "spot_name": "Кафе на полянке",
    "fiscal_companies": [
      {
        "fiscal_company_id": 1,
        "uuid": "test-uuid",
        "inn": "001234567890",
        "taxes": [
          {
            "tax_id": 1,
            "tax_name": "Без налога"
          }
        ]
      }
    ]
  }
]
 

```

Метод возвращает список заведений с их фискальными компаниями

### HTTP запрос

`GET https://joinposter.com/api/spots.getSpotFiscalCompanies`

### Параметры ответа spots.getSpotInvoiceData

Ответ | описание
--------- | -----------
массив объектов | Список заведений

`объект заведения` содержит следующую структуру:

Параметра | Тип    | Описание
--------- |--------| -----------
spot_id | int    | Идентификатор заведения
spot_name | string | Название заведения
fiscal_companies | array  | Список фискальных компаний


`fiscal_companies` массив содержит объекты формата:

Параметра | Тип    | Описание
--------- |-----| -----------
fiscal_company_id | int | Идентификатор фискальной компании
uuid | string | Уникальный идентификатор фискальной компании
inn | string | ИНН фискальной компании
taxes | array | Список налогов

`taxes` массив содержит объекты формата:

Параметра | Тип    | Описание
--------- |-----| -----------
tax_id | int | Идентификатор налога
tax_name | string | Название налога
