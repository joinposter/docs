## finance.getAccounts: Get Accounts

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/finance.getAccounts'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);
```

> Response example:

```json
{
  "response":[
    {
      "account_id":"1",
      "name":"Наличные в заведении",
      "currency_id":"2",
      "type":"3",
      "balance":"545643467264",
      "balance_start":"200000000",
      "percent_acquiring":"0.00",
      "currency_symbol":"<i class=\"icon-rouble\"><\/i>",
      "currency_code_iso":"RUB",
      "currency_code":"руб."
    },
    {
      "account_id":"2",
      "name":"Счет ИП",
      "currency_id":"2",
      "type":"1",
      "balance":"83086475682",
      "balance_start":"790000",
      "percent_acquiring":"0.00",
      "currency_symbol":"<i class=\"icon-rouble\"><\/i>",
      "currency_code_iso":"RUB",
      "currency_code":"руб."
    },
    {
      "account_id":"3",
      "name":"Сейф",
      "currency_id":"2",
      "type":"3",
      "balance":"56720000",
      "balance_start":"65000000",
      "percent_acquiring":"0.00",
      "currency_symbol":"<i class=\"icon-rouble\"><\/i>",
      "currency_code_iso":"RUB",
      "currency_code":"руб."
    }
  ]
}
```

The method returns accounts in the Finance section

### HTTP request

`GET https://joinposter.com/api/finance.getAccounts`

### GET parameters of the finance.getAccounts response

Parameter | Description
--------- | -----------
type | Type of account: 1—non-cash, 2—bank card, 3—cash. The default value is all accounts.

### The finance.getAccounts response parameters

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an array of objects with the following parameters inside each of them:

Parameter | Description
--------- | -----------
account_id | Order ID
name | Account name
type | Type of account: 1—non-cash, 2—bank card, 3—cash
balance | Account balance in hryvnias/rubles
balance_start | The opening balance in hryvnias/rubles, the balance of money at the time of creation
percent_acquiring | Acquiring interest
currency_id | Currency ID in Poster: 1—hryvnia, 2—ruble, 3—dollar, 4—euro, 5—tenge, 6—lari, 7—baht, 8—Armenian dram
currency_name | Currency name
currency_code | Currency code on the register
currency_symbol | Unicode currency symbol; for the ruble, dram, and manat, HTML comes displayed on the register as a currency icon
currency_code_iso | Digital currency code according to the ISO 4217 standard

