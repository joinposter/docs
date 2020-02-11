## finance.getTransactions: Get All Transactions

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/finance.getTransactions'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&dateFrom=20170701'
 . '&dateTo=20170901';


$data = sendRequest($url);

```

> Response example:

```json
{
  "response":[
    {
      "transaction_id":"538",
      "account_id":"1",
      "user_id":"1",
      "category_id":"7",
      "type":"0",
      "amount":"-8137663",
      "balance":"545516997964",
      "date":"2017-08-31 09:20:22",
      "recipient_type":"0",
      "recipient_id":"0",
      "binding_type":"15",
      "binding_id":"400",
      "comment":"Корректирующая транзакция",
      "delete":"0",
      "account_name":"Наличные в заведении",
      "currency_symbol":"<i class=\"icon-rouble\"><\/i>",
      "category_name":"Actualization"
    },
    {
      "transaction_id":"536",
      "account_id":"1",
      "user_id":"1",
      "category_id":"2",
      "type":"1",
      "amount":"8148663",
      "balance":"545525135627",
      "date":"2017-08-31 09:20:21",
      "recipient_type":"0",
      "recipient_id":"0",
      "binding_type":"11",
      "binding_id":"400",
      "comment":"Закрытие наличной кассы",
      "delete":"0",
      "account_name":"Наличные в заведении",
      "currency_symbol":"<i class=\"icon-rouble\"><\/i>",
      "category_name":"Cash register shifts"
    }
  ]
}
```

The method returns all transactions

### HTTP request

`GET https://joinposter.com/api/finance.getTransactions`

### GET parameters of the finance.getTransactions request

Parameter | Description
--------- | -----------
account_id | An optional parameter, the account ID; the default value is for all accounts
category_id | An optional parameter, the category ID; the default value is for all categories
dateFrom | An optional parameter, the sampling start date in the `Ymd` format, inclusive. The default date is a month ago.
dateTo | An optional parameter, the sampling end date in the `Ymd` format, inclusive. The default date is the current date.
pretty | An optional parameter, return data in a human-readable format. All system transactions will be reduced to incoming or expendable transactions.

### The finance.getTransactions response parameters

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an array, each element of which contains the following parameters:

Parameter | Description
--------- | -----------
transaction_id | Transaction ID
account_id | Order ID
user_id | Waiter ID
category_id | Category ID; the default value is all categories
type | Transaction type: 0—expenditure, 1—income
amount | Transaction amount in kopecks
balance | Account balance in kopecks
date | Date of transaction
recipient_type | Type of the recipient entity: 1—transfer, 12—supplier
recipient_id | Recipient entity ID
binding_type | The type of the corresponding entity: 1—transfer, 12 —register-shift closing, 13—supply, 14—register-shift transactions
binding_id | The corresponding entity ID
comment | Comment
account_name | Account name
category_nam | Category name
currency_symbol | Unicode currency symbol; for the ruble, dram, and manat, HTML comes displayed on the register as a currency icon

