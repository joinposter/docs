## spots.getSpotFiscalCompanies: Get locations fiscal companies data

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/spots.getSpotFiscalCompanies'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = PosterAPI::sendRequest($url);
```

> Response example:

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

Method returns fiscal companies of all locations

### HTTP request

`GET https://joinposter.com/api/spots.getSpotFiscalCompanies`

### Response from spots.getSpotInvoiceData

Response | Description
--------- | -----------
array of objects | List of spots

`spot object` contains object with next params:

Parameter | type  | Description
--------- |-------| -----------
spot_id | int   | Location id
spot_name | string | Location name
fiscal_companies | array | List of fiscal companies


`fiscal_companies` contains object with next params:

Parameter | type | Description
--------- |-----| -----------
fiscal_company_id | int | Fiscal company id
uuid | string | Fiscal company unique id
inn | string | Fiscal company inn
taxes | array | List of taxes

`taxes` contains object with next params:

Parameter | type | Description
--------- |-----| -----------
tax_id | int | Tax id
tax_name | string | Tax name
