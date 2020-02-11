## dash.getTransactionHistory: Transaction History

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/dash.getTransactionHistory'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&transaction_id=388678';

$data = sendRequest($url);
```

> Response example:

```json
{
  "response":[
    {
      "transaction_id":"388678",
      "type_history":"print",
      "time":"1507703522429",
      "value":"1",
      "value2":"2147483647",
      "value3":"0",
      "value_text":null,
      "spot_tablet_id":"1"
    },
    {
      "transaction_id":"388678",
      "type_history":"close",
      "time":"1507703520358",
      "value":"3",
      "value2":"145000",
      "value3":"0",
      "value_text":"{\"payments\":{\"cash\":1450}}",
      "spot_tablet_id":"1"
    },
    {
      "transaction_id":"388678",
      "type_history":"additem",
      "time":"1507703508927",
      "value":"168",
      "value2":"0",
      "value3":"0",
      "value_text":"{\"price\":450}",
      "spot_tablet_id":"1"
    },
    {
      "transaction_id":"388678",
      "type_history":"open",
      "time":"1507703507594",
      "value":"1",
      "value2":"95",
      "value3":"3",
      "value_text":null,
      "spot_tablet_id":"1"
    }
  ]
}
```

The method returns a transaction history

### HTTP request

`GET https://joinposter.com/api/dash.getTransactionHistory`

### GET parameters of the dash.getTransactionHistory request

Parameter | Description
--------- | -----------
transaction_id | A mandatory parameter, the transaction ID (order number)

### Dash.getTransactionHistory response parameters

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an array of objects with the following parameters inside each of them:

Parameter | Description
--------- | -----------
transaction_id | Order number
type_history | An operation on an order; the possible values are described below
time | Operation time in the unixtimestamp format
spot_tablet_id | Register ID
value_text | A text value that corresponds to a specific operation. May contain json as well.
value, value2, value3 | Depending on type_history, it means the following:

Values of the `value`, `value2`, `value3` parameters depending on `type_history`:

### open—The bill is open

- value—Waiter ID 
- value2—Table ID
- value3—0

### comment—Comment added

- value—0 
- value2—0 
- value3—0
- value_text—comment value  

### close—The receipt is printed and the bill closed

- value—0 
- value2—Total amount 
- value3—0
- value_text—JSON line. The `paymets` property contains an object with the following properties: `cash`—the amount paid by cash, `card`—by credit card, `cert`—by a gift card.  

### delete—The order is removed

- value—Product ID 
- value2—0
- value3—Modifier ID. In case of no modifier, it’s 0

### print—A receipt is printed

- value—Waiter ID 
- value2—Time
- value3—0 

### sendtokitchen—A ticket is sent to the kitchen

- value—Product ID
- value2—Modifier ID. In case of no modifier, it’s 0 
- value3—Product count 

### additem—Product added

- value—Added product ID
- value2—0 
- value3—Modifier ID. In case of no modifier, it’s 0
- value_text—A JSON line with a `price` property—the price of the product added to the order

### settable—Set another table for the order

- value—Table ID 
- value2—0
- value3—0 

### changeitemcount—Product count updated; if `value2` is 0, the product has been removed

- value—Product ID 
- value2—Product count
- value3—Modifier ID. In case of no modifier, it’s 0  

### deleteitem—Product removed

- value—Removed product ID
- value2—0 
- value3—Modifier ID. In case of no product modifier, it’s 0

### setclient—Customer added

- value—Customer ID
- value2—Discount amount
- value3—0

