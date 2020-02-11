## settings.getCurrency: Account Currency

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/settings.getCurrency'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);
```

> Response example:

```json
{  
  "response":{  
    "currency_id":"2",
    "currency_name":"Рубль",
    "currency_code":"руб.",
    "currency_symbol":"<i class=\"icon-rouble\"><\/i>",
    "currency_code_iso":"RUB"
  }
}
```

The method returns the account currency

### HTTP request

`POST https://joinposter.com/api/settings.getCurrency`

### The settings.getCurrency response parameters

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an object containing the following parameters:

Parameter | Description
--------- | -----------
currency_id | Currency ID in Poster
currency_name | Currency name
currency_code | Currency code on the register
currency_symbol | Unicode currency symbol; for the ruble, dram, and manat, HTML comes displayed on the register as a currency icon
currency_code_iso | Digital currency code according to the ISO 4217 standard

