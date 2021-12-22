## transactions.getTransactions: Order List

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/transactions.getTransactions'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&date_from=2017-11-30'
 . '&date_to=2017-11-30'
 . '&per_page=10'
 . '&page=5';

$data = sendRequest($url);
```

> Response example:

```json
{  
  "response":{  
    "count":41,
    "page":{  
      "per_page":10,
      "page":5,
      "count":1
    },
    "data":[  
      {  
        "transaction_id":25221,
        "table_id":1,
        "spot_id":1,
        "client_id":68,
        "sum":360,
        "payed_sum":0,
        "payed_cash":0,
        "payed_card":0,
        "payed_cert":0,
        "payed_bonus":0,
        "payed_third_party":0,
        "round_sum":0,
        "pay_type":3,
        "reason":0,
        "tip_sum": 0,
        "bonus":0,
        "discount":100,
        "print_fiscal":0,
        "date_close":"2017-11-30 13:48:09",
        "products":[  
          {  
            "product_id":469,
            "modification_id":0,
            "type":2,
            "workshop_id":2,
            "num":2,
            "product_sum":360,
            "payed_sum":0,
            "cert_sum":0,
            "fiscal_company_id": 0,
            "bonus_sum":0,
            "bonus_accrual":0,
            "round_sum":0,
            "discount":100,
            "tax_fiscal":1
          }
        ]
      }
    ]
  }
}
```

The method returns an order list of with products in the date range and pagination

### HTTP GET request

`https://joinposter.com/api/transactions.getTransactions`

### GET parameters of the transactions.getTransactions request

Parameter | Description
--------- | -----------
date_from | Sampling start date in the “Y-m-d” format
date_to | Sampling end date in the “Y-m-d” format
per_page | Orders count on one page. By default, it takes 100; the maximum value is 1000.
page | Page number, the default number is 1

### The transactions.getTransactions response parameters

Inside the `response` parameter, there is an object containing the following parameters:

Parameter | Description
--------- | -----------
count | Total order count in the selected date range
page | Page info
data | Order information

Inside the `page` parameter, there is an object containing the following parameters:

Parameter | Description
--------- | -----------
per_page | Orders count on one page
page | Current page number
count | Orders count on the current page

Inside the `data` parameter, there is an array, each element of which contains the following parameters:

Parameter | Description
--------- | -----------
transaction_id | Order ID
table_id | Table ID
spot_id | Location ID
client_id | Customer ID
sum | Total order amount
payed_sum | The total amount paid, `from payed_cash` and `payed_card`
payed_cash | The amount paid by cash
payed_card | The amount paid by bank transfer
payed_cert | The amount paid by a gift card
payed_bonus | The amount paid by points
payed_third_party | The аmount paid by third-party
round_sum   | Receipt rounding amount
pay_type | Type of payment: 0—closed without payment, 1—payment by cash, 2—payment by bank transfer, 3—mixed payment
reason | Reason for closing the bill without payment: 1—the customer has left, 2—on the house, 3—a waiter’s error
tip_sum | Service fee amount
bonus | An accrued point as a percentage of `payed_sum`
discount | Order discount in percentage
print_fiscal | The status of printing a fiscal receipt: 0 — have not printed, 1 — have printed, 2 — fiscal return
date_close | Order closing date in the “Y-m-d H:i:s” format
products | Order products

The `products` parameter has an array inside, each element of which contains the following parameters:

Parameter | Description
--------- | -----------
product_id | Product ID
modification_id | Modification ID
type | Product type: 2—dish, 3—product
workshop_id | Station ID
num | Product count in an order
product_sum | Product cost
payed_sum | Amount paid
cert_sum | The amount paid by a gift card
bonus_sum | The amount paid by points
bonus_accrual | Points accrued
round_sum   | Rounding amount
discount | Discount on a product in percents
tax_fiscal | Tax on a fiscal printer

