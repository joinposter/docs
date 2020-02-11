## dash.getTransactionProducts: List of Transaction Products

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/dash.getTransactionProducts'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&transaction_id=388678';
 
$data = sendRequest($url);
```

> Response example:

```json
{
  "response":[
    {
      "product_id":"908",
      "product_name":"Пицца сборная",
      "modification_id":"68",
      "modificator_name":"Сыр, Грибы, Ох. колбаски, Оливки, Средняя Ø35см",
      "modificator_barcode":"",
      "modificator_product_code":"",
      "weight_flag":"0",
      "num":"1",
      "time":"1507703516999",
      "workshop":"2",
      "barcode":"",
      "product_code":"",
      "tax_id":"4",
      "nodiscount":"1",
      "payed_sum":"45000",
      "product_sum":"45000",
      "discount":"0",
      "bonus_sum":"0",
      "round_sum":0,
      "client_id":"0",
      "promotion_id":"0",
      "cert_sum":"0",
      "product_cost":"43",
      "product_cost_netto":"36",
      "product_profit":"42707",
      "product_profit_netto":"42700",
      "bonus_accrual":"0",
      "tax_value":"5",
      "tax_type":"2",
      "tax_fiscal":"1",
      "category_id":"33"
    },
    {
      "product_id":"169",
      "product_name":"Речная форель в фольге",
      "modification_id":"0",
      "modificator_name":null,
      "modificator_barcode":null,
      "modificator_product_code":null,
      "weight_flag":"0",
      "num":"1",
      "time":"1507703509384",
      "workshop":"2",
      "barcode":"",
      "product_code":"",
      "tax_id":"4",
      "nodiscount":"1",
      "payed_sum":"55000",
      "product_sum":"55000",
      "discount":"0",
      "bonus_sum":"0",
      "round_sum":0,
      "client_id":"0",
      "promotion_id":"0",
      "cert_sum":"0",
      "product_cost":"4340",
      "product_cost_netto":"3617",
      "product_profit":"47910",
      "product_profit_netto":"47187",
      "bonus_accrual":"0",
      "tax_value":"5",
      "tax_type":"2",
      "tax_fiscal":"1",
      "category_id":"33"
    },
    {
      "product_id":"168",
      "product_name":"Стейк из сёмги",
      "modification_id":"0",
      "modificator_name":null,
      "modificator_barcode":null,
      "modificator_product_code":null,
      "weight_flag":"0",
      "num":"1",
      "time":"1507703508927",
      "workshop":"2",
      "barcode":"",
      "product_code":"",
      "tax_id":"4",
      "nodiscount":"1",
      "payed_sum":"45000",
      "product_sum":"45000",
      "discount":"0",
      "bonus_sum":"0",
      "round_sum":0,
      "client_id":"0",
      "promotion_id":"0",
      "cert_sum":"0",
      "product_cost":"2213",
      "product_cost_netto":"1844",
      "product_profit":"40537",
      "product_profit_netto":"40168",
      "bonus_accrual":"0",
      "tax_value":"5",
      "tax_type":"2",
      "tax_fiscal":"1",
      "category_id":"33"
    }
  ]
}
```

The method returns a product list by a transaction

### HTTP request

`GET https://joinposter.com/api/dash.getTransactionProducts`

### GET parameters of the dash.getTransactionProducts request

Parameter | Description
--------- | -----------
transaction_id | A mandatory parameter, the transaction ID (order number)

### The dash.getTransactionProducts response parameters

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an object containing the following parameters:

Parameter | Description
--------- | -----------
product_id | Product ID
product_name | Product name
modification_id | Modifier ID. In case of no modifier, it’s 0.
modificator_name | Modifier name
modificator_barcode | Modifier barcode
modificator_product_code | Modifier SKU
num | Product count in an order
time | The time of the last update of the product count in an order; is measured in milliseconds
workshop | Station ID
barcode | Product barcode
product_code | Product SKU
tax_id | Tax ID
fiscal | A fiscal receipt status: 1—fiscal, 0—non-fiscal
nodiscount | The status of discounts and points applying to products: 0—yes, 1—no
payed_sum | Amount paid in kopecks
product_sum | Product cost in kopecks
discount | The discount applied to the order
bonus_sum | The point amount in dollars
round_sum   | Rounding amount in kopecks
client_id | Customer ID
promotion_id | Promotion ID
cert_sum | The amount paid by a gift card
product_cost | Product food cost
product_cost_netto | Product food cost without VAT in cents. Is returned if the 'Calculate cost and net profit' setting is enabled
product_profit | Profit
product_profit_netto | Profit without VAT in cents. Is returned if the 'Calculate cost and net profit' setting is enabled
bonus_accrual | Points accrued
tax_value | Tax percentage of an order amount
tax_type | Tax type: 1—VAT, 2—turnover tax
tax_fiscal | Tax on a fiscal printer
category_id | Product category ID
