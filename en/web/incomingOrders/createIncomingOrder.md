## incomingOrders.createIncomingOrder: Create an Online Order

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/incomingOrders.createIncomingOrder'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$incoming_order = [
    'spot_id'   => 1,
    'phone'     => '+380680000000',
    'products'  => [
        [
            'product_id' => 169,
            'count'      => 1
        ],
    ],
];

$data = sendRequest($url, 'post', $incoming_order);
```

> Response example:

```json
{  
  "response":{  
    "incoming_order_id":2,
    "spot_id":1,
    "status":0,
    "client_id":0,
    "first_name":null,
    "last_name":null,
    "phone":null,
    "email":null,
    "sex":null,
    "birthday":null,
    "address":null,
    "comment":null,
    "created_at":"2017-10-27 11:47:19",
    "updated_at":"2017-10-27 11:47:19",
    "transaction_id":null,
    "fiscal_spreading":0,
    "fiscal_method":"",
    "products":[  
      {  
        "io_product_id":2,
        "product_id":169,
        "modificator_id":null,
        "incoming_order_id":2,
        "count":1,
        "created_at":"2017-10-27 11:47:19"
      }
    ]
  }
}
```

> Request example с автоприменением акций:

```php
<?php
$url = 'https://joinposter.com/api/incomingOrders.createIncomingOrder'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$incoming_order = [
    "spot_id"   => 1,
    "products"  => [
        [
            "product_id"    => 139,
            "count"         => 1
        ]
    ],
    "promotion" => [
        [
            "id" => 1, 
            "involved_products" => [
                ["id" => 139, "count"  => 1]
            ],
            "result_products"   => [
                ["id" => 161]
            ]
        ]
    ]
];

$data = sendRequest($url, 'post', $incoming_order);
```

> Response example:

```json
{
  "response":{
    "incoming_order_id":"106",
    "type":"1",
    "spot_id":"1",
    "status":0,
    "client_id":0,
    "first_name":null,
    "last_name":null,
    "phone":null,
    "email":null,
    "sex":null,
    "birthday":null,
    "address":null,
    "comment":null,
    "created_at":"2017-12-06 18:45:06",
    "updated_at":"2017-12-06 18:45:06",
    "transaction_id":null,
    "fiscal_spreading":"0",
    "fiscal_method":"",
    "promotion":"[{\"id\":1,\"involved_products\":[{\"id\":139,\"count\":1}],\"result_products\":[{\"id\":161}]}]",
    "products":[
      {
        "io_product_id":"194",
        "product_id":"139",
        "modificator_id":null,
        "incoming_order_id":"106",
        "count":"1.00000",
        "created_at":"2017-12-06 18:45:06"
      }
    ]
  }
}
```

The method creates an online order

### HTTP POST request

`POST https://joinposter.com/api/incomingOrders.createIncomingOrder`

### POST parameters of the incomingOrders.createIncomingOrder request

Parameter | Description
--------- | -----------
spot_id | Location ID the online order will come to
client_id | Customer ID in Poster; if ID is not specified, the `phone` parameter should be transmitted. Poster will try to find a customer with the same phone number and attach him to the order. If it is a new customer, the waiter will select a group for him, and Poster will create a new customer.
first_name | The customer’s name; by default, it is not transmitted.
last_name | The customer’s last name; by default, it is not transmitted.
phone | Customer’s phone number; a mandatory parameter if `client_id` is not specified
email | Email; is not transmitted by default
sex | Customer gender: 0—not specified, 1—male, 2—female. By default, it is not transmitted.
birthday | Customer’s birthday in a `Y-m-d` format. By default, it is not transmitted.
address | Customer’s address; by default, it is not transmitted
comment | Online order comment; by default, it is not transmitted
products | Product list
payment | Payment information; by default, it is not transmitted
promotion | List of promotions to be applied to the order

The `products` parameter should contain an array, each element of which should contain the following parameters:

Parameter | Description
--------- | -----------
product_id | Product ID
modificator_id | Product modifier ID
modification | Dish modifications; are not transmitted by default
count | A mandatory parameter, product count
price | The price of goods in kopecks, by default the price of the goods in the indicated institution is taken

The `modification` parameter should contain a JSON `line`. JSON should consist of an array of objects, each of which should contain the following parameters:

Parameter | Description
--------- | -----------
m | Dish modification ID
a | Dish modifications count

The `payment` parameter should contain an object containing the following parameters:

Parameter | Description
--------- | -----------
type | The status confirming a prepayment: 0—it has not been done, 1—it has been done. The default value is 0.
sum | The amount paid in kopecks
currency | The ISO currency code of the payment; it must match the account currency, for example, UAH—hryvnia, RUB—ruble, USD—dollar

!> If there was no prepayment in the online order, do not send the array `payment` in the request.

The `promotion` parameter contains an array of objects, each of which contains the following parameters:

Parameter | Description
--------- | -----------
id | Promotion ID to be applied
involved_products | An array of products that participate in a promotion.
result_products | An array of products that are the result of a promotion. It should be transmitted in points-based promotions only.

The `involved_products` array contains objects with the following properties:

Parameter | Description
--------- | -----------
id | A mandatory parameter; the ID of a product that participates in a promotion
count | A mandatory parameter; the product count participating in a promotion
modification | An optional parameter; the modification ID that participates in the promotion

<aside class="info">
    The products transmitted in the “result_products” array should not be included in the order. 
    The register will add them automatically.
</aside>

The `result_products` array contains objects with the following properties:

Parameter | Description
--------- | -----------
id | A mandatory parameter; the ID of a product to be added to the order as a result of the promotion
count | A mandatory parameter; the product count to be added to the order
modification | An optional parameter; the modification ID to be added as the result of the promotion

### incomingOrders.createIncomingOrder response parameters

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an object containing the following parameters:

Parameter | Description
--------- | -----------
incoming_order_id | Online order ID
type | Order type: 1—online order, 2—reservation. For this method, it always equals 2.
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
fiscal_spreading | An optional parameter. A status of sending products to a fiscal printer: 1—send only fiscal products, 2—send all products, 3—not to send products.
fiscal_method | An optional parameter, a payment method on the fiscal printer: cash—by cash, card—by credit card. The default value is cash.
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

