## dash.getTransactions: Transaction List

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/dash.getTransactions'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&dateFrom=20170905'
 . '&dateTo=20170908';

$data = sendRequest($url);
```

> Response example:

```json
{
  "response":[
    {
      "transaction_id":"384960",
      "date_start":"1504641602936",
      "date_start_new":"1504641602941",
      "date_close":"1504641603008",
      "status":"2",
      "guests_count":"4",
      "discount":"0",
      "bonus":"0",
      "pay_type":"3",
      "payed_bonus":"0",
      "payed_card":"0",
      "payed_cash":"199140",
      "payed_sum":"199140",
      "payed_cert":"0",
      "tip_sum":"0",
      "sum":"180600",
      "spot_id":"1",
      "table_id":"90",
      "name":"Demo",
      "user_id":"1",
      "client_id":"0",
      "card_number":"0",
      "transaction_comment":null,
      "reason":"",
      "print_fiscal":"0",
      "total_profit":"172828",
      "table_name":"1",
      "client_firstname":null,
      "client_lastname":null,
      "date_close_date":"2017-09-05 23:00:03"
    },
    {
      "transaction_id":"384956",
      "date_start":"1504641601797",
      "date_start_new":"1504641601809",
      "date_close":"1504641601850",
      "status":"2",
      "guests_count":"5",
      "discount":"0",
      "bonus":"0",
      "pay_type":"3",
      "payed_bonus":"0",
      "payed_card":"0",
      "payed_cash":"117000",
      "payed_sum":"117000",
      "payed_cert":"0",
      "tip_sum":"0",
      "sum":"117000",
      "spot_id":"1",
      "table_id":"91",
      "name":"Максим",
      "user_id":"2",
      "client_id":"0",
      "card_number":"0",
      "transaction_comment":null,
      "reason":"",
      "print_fiscal":"0",
      "total_profit":"113487",
      "table_name":"2",
      "client_firstname":null,
      "client_lastname":null,
      "date_close_date":"2017-09-05 23:00:02"
    }
  ]
}
```

The method returns a list of transactions

### HTTP request

`GET https://joinposter.com/api/dash.getTransactions`

### GET parameters of the dash.getTransactions request

Parameter | Description
--------- | -----------
dateFrom | An optional parameter, the sampling start date in the `Ymd` format, inclusive. The default date is a month ago.
dateTo | An optional parameter, the sampling end date in the `Ymd` format, inclusive. The default date is the current date.
type | Reports type: `waiters`—by waiter, `spots`—by location, `clients`—by customer. When using, be sure to specify `id`.
id | The ID of the entity to receive reports to; if not specified, transactions for all reports types will be displayed. When using, be sure to specify the `type`.
status | Transaction status: 0—all transactions, 1—only the open ones, 2—only the closed ones, 3—the removed ones
include_products | The status of including products in transactions in response: `true`—to include, `false`—not to
include_history | The status of including a transaction history in response, `true`—to include, `false`—not to
next_tr | The ID of the transaction to be followed by getting a transaction list
after_date_close | Transactions after the closing date in the unixtimestamp format
before_date_close | Transactions before the closing date in the unixtimestamp format
timezone | An optional parameter; if it equals `client`, the date is returned in the account time zone.

### dash.getTransactions response parameters

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an array of objects with the following parameters inside each of them:

Parameter | Description
--------- | -----------
date_start | The order opening date in the unixtimestamp format
date_close | The order closing date in the unixtimestamp format, 0—if the order is still open
status | Order status: 1—open, 2—closed, 3—removed
guests_count | Seat count
name | Waiter’s name
discount | Percentage minus
bonus | An accrued point as a percentage of `payed_sum`
pay_type | Payment type: 0—closed without payment (the cause is in `reason`), 1—cash payment, 2—card payment, 3—mixed payment
payed_bonus | The amount paid by points in cents
payed_card | The amount paid by credit card in cents
payed_cash | The amount paid in cash in cents
payed_sum | The amount paid by hard cash which is equal to the `payed_cash` amount plus `payed_card`
payed_third_party | The amount paid by third-party in cents
round_sum   | Receipt rounding amount in cents
sum | Total order amount, without discounts, in cents
spot_id | Location ID
table_id | Table ID
user_id | Waiter ID
client_id | Customer ID
transaction_comment | Order comment
reason | Reason for closing the bill without payment: 1—the customer has left, 2—on the house, 3—a waiter’s error
print_fiscal | The status of printing a fiscal receipt: 0 — have not printed, 1 — have printed, 2 — fiscal return
total_profit | Profit amount
total_profit_netto | Profit amount without VAT. Is returned if the 'Calculate cost and net profit' setting is enabled
table_name | Table name
client_firstname | Customer first name
client_lastname | Customer last name
products | Product array in an order
history | History of order operations. Contains an array of objects; see the [dash.getTransactionHistory](/en/docs/v3/web/dash/getTransactionHistory) method for a description of the object parameters

Inside the `products` parameter, there is an array of objects, each with the following parameters inside:

Parameter | Description
--------- | -----------
product_id | Product ID
modification_id | Modification ID
product_price | Product cost
num | Product count in an order
payed_sum | The amount paid
product_cost | Product food cost in cents
product_cost_netto | Product food cost without VAT in cents. Is returned if the 'Calculate cost and net profit' setting is enabled
product_profit | Product profit in cents
product_profit_netto | Product profit without VAT in cents. Is returned if the 'Calculate cost and net profit' setting is enabled
