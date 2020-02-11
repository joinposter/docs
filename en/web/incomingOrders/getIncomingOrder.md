## incomingOrders.getIncomingOrder: Online Order Properties

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/incomingOrders.getIncomingOrder'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&incoming_order_id=1';

$data = sendRequest($url);
```

> Response example:

```json
{  
  "response":{  
    "incoming_order_id":1,
    "spot_id":1,
    "status":1,
    "client_id":0,
    "first_name":"Антон",
    "last_name":"Талышкин",
    "phone":"79630313844",
    "email":"contact@joinposter.com",
    "sex":1,
    "birthday":"1986-11-23",
    "address":"ул. Малышева, 3",
    "comment":"",
    "created_at":"2017-10-26 14:58:02",
    "updated_at":"2017-10-26 15:25:17",
    "transaction_id":1949,
    "products":[  
      {  
        "io_product_id":1,
        "product_id":113,
        "modificator_id":null,
        "incoming_order_id":1,
        "count":1,
        "created_at":"2017-10-26 14:58:02"
      }
    ]
  }
}
```

The method returns the properties of the online order

### HTTP GET request

`https://joinposter.com/api/incomingOrders.getIncomingOrder`

### GET parameters of the incomingOrders.getIncomingOrder request

Parameter | Description
--------- | -----------
incoming_order_id | Online order ID

### incomingOrders.getIncomingOrder response parameters

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an object containing the following parameters:

Parameter | Description
--------- | -----------
incoming_order_id | Online order ID
spot_id | Location ID
status | Order status: 0—new, 1—accepted, 7—canceled
client_id | Customer ID
first_name | Customer first name
last_name | Customer last name
phone | Customer phone number
email | Customer’s email
sex | Customer gender: 0—not specified, 1—male, 2—female
birthday | Customer’s birthday in a `Y-m-d` format
address | Customer address
comment | Online order comment
created_at | Online order creation date
updated_at | Online order status update date
transaction_id | Associated order ID
products | Product list

The `products` parameter has an array inside, each element of which contains the following parameters:

Parameter | Description
--------- | -----------
io_product_id | Online order product ID
product_id | Product ID
modificator_id | Product modifier ID
incoming_order_id | Online order ID
count | Online order product count
created_at | Date of adding the product to the online order

