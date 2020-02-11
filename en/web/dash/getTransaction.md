## dash.getTransaction: Transaction Receiving

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/dash.getTransaction'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&transaction_id=330660'
 . '&include_history=true'
 . '&include_products=true';

$data = sendRequest($url);
```

> Response example:

```json
{
   "response":[
      {
         "transaction_id":"330660",
         "date_start":"1518873040083",
         "date_start_new":"1518873041556",
         "date_close":"1518873046314",
         "status":"2",
         "guests_count":"2",
         "discount":"0",
         "bonus":"0",
         "pay_type":"3",
         "payed_bonus":"0",
         "payed_card":"0",
         "payed_cash":"2750",
         "payed_sum":"2750",
         "payed_cert":"0",
         "payed_third_party":"0",
         "round_sum":"0",
         "tip_sum":"0",
         "tips_card": "0",
         "tips_cash": "0",
         "sum":"2750",
         "spot_id":"1",
         "table_id":"94",
         "name":"Анна",
         "user_id":"1",
         "client_id":"0",
         "card_number":"0",
         "transaction_comment":null,
         "reason":"",
         "print_fiscal":"0",
         "total_profit":"-8786",
         "total_profit_netto":"-6789",
         "table_name":"5",
         "client_firstname":null,
         "client_lastname":null,
         "date_close_date":"2018-02-17 16:10:46",
         "products":[
            {
               "product_id":"162",
               "modification_id":"0",
               "num":"1",
               "product_price":"1050",
               "payed_sum":"1050",
               "product_cost":"4536",
               "product_cost_netto":"3780",
               "product_profit":"-3486",
               "product_profit_netto":"-2905"
            },
            {
               "product_id":"161",
               "modification_id":"0",
               "num":"1",
               "product_price":"1700",
               "payed_sum":"1700",
               "product_cost":"7000",
               "product_cost_netto":"5833",
               "product_profit":"-5300",
               "product_profit_netto":"-3884"
            }
         ],
         "history":[
            {
               "history_id":"2485357",
               "type_history":"open",
               "spot_tablet_id":"1",
               "time":"1518873040083",
               "user_id":"1",
               "value":"1",
               "value2":"94",
               "value3":"2",
               "value4":"0",
               "value5":"0",
               "value_text":null
            },
            {
               "history_id":"2485358",
               "type_history":"additem",
               "spot_tablet_id":"1",
               "time":"1518873041556",
               "user_id":"1",
               "value":"162",
               "value2":"0",
               "value3":"0",
               "value4":"0",
               "value5":"0",
               "value_text":{
                  "price":10.5
               }
            },
            {
               "history_id":"2485359",
               "type_history":"additem",
               "spot_tablet_id":"1",
               "time":"1518873042008",
               "user_id":"1",
               "value":"161",
               "value2":"0",
               "value3":"0",
               "value4":"0",
               "value5":"0",
               "value_text":{
                  "price":17
               }
            },
            {
               "history_id":"2485360",
               "type_history":"close",
               "spot_tablet_id":"1",
               "time":"1518873046314",
               "user_id":"1",
               "value":"3",
               "value2":"2750",
               "value3":"0",
               "value4":"0",
               "value5":"0",
               "value_text":{
                  "payments":{
                     "cash":27.5
                  }
               }
            }
         ]
      }
   ]
}
```

The method returns a list with one transaction

### HTTP request

`GET https://joinposter.com/api/dash.getTransaction`

### GET parameters of the dash.getTransaction request

Parameter | Description
--------- | -----------
transaction_id | A mandatory parameter, an order number to return information to
include_products | The status of including products in transactions in response: `true`—to include, `false`—not to
include_history | The status of including a transaction history in response, `true`—to include, `false`—not to
timezone | An optional parameter; if it equals `client`, the date is returned in the account time zone.
type | Reports type: `waiters`—by waiter, `spots`—by location, `clients`—by customer. When using, be sure to specify `id`.
id | The ID of the entity to receive reports to; if not specified, transactions for all reports types will be displayed. When using, be sure to specify the `type`.
status | Transaction status: 0—all transactions, 1—only the open ones, 2—only the closed ones, 3—the removed ones

### Dash.getTransaction response parameters

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
tip_sum | The amount of service charge in cents
tips_card | The amount of tip payed by card in cents
tips_cash | The amount of tip payed by cash in cents
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
