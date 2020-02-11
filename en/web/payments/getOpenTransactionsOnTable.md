## payments.getOpenTransactionsOnTable: List of Open Orders on the Table

> Request example:

```php
<?
$url = 'https://joinposter.com/api/payments.getOpenTransactionsOnTable?' .
  'format=json';

$application_secret = '123123123123';

$request = [
  'type' => 'application-name',
  'merchant_id' => 3432343,
  'table_id' => 41,
];

$request['sign'] = md5(implode(':', $request) . ':' . $application_secret);

$url .= '&' . http_build_query($request);

$answer = sendRequest($url);
```

> Response example:

```json
{
  "response":[
    {
      "order_id":30139,
      "transaction_id":1484233370643,
      "date_open":1484233375235,
      "payed_sum":127.02,
      "products":[
        {
          "product_name":"Венский суп Гуляш"
        },
        {
          "product_name":"Медальоны из телятины с овощами гриль"
        },
        {
          "product_name":"Хлеб белый собственной выпечки"
        },
        {
          "product_name":"Кальян",
          "modificator_name":"на соке"
        },
        {
          "product_name":"Соус BBQ к блюду"
        },
        {
          "product_name":"Pepsi 300 ml"
        }
      ]
    },
    {
      "order_id":30946,
      "transaction_id":1485341938799,
      "date_open":1485341938872,
      "payed_sum":190,
      "products":[
        {
          "product_name":"Кролик по-охотничьи"
        }
      ]
    }
  ]
}
```

It returns orders to an external payment service that are currently open on a particular table.

### HTTP request

`GET https://joinposter.com/api/payments.getOpenTransactionsOnTable`

### GET parameters of the payments.getOpenTransactionsOnTable request

Parameter | Description
--------- | -----------
type | The key name of a payment system that sends the request. Under the system, a separate application is created in the Poster system, where the given name is specified.
merchant_id | Poster customer ID in the internal database of the payment system
table_id | Table ID to receive open orders for
sign | The request signature that is an md5 hash of a line connecting the values of the following variables through the colon: type, merchant_id, table_id, application_secret.

application_secret is an application secret line. Like the type variable, it is issued to the payment system while creating an application for it in Poster.

### The payments.getOpenTransactionsOnTable response parameters

Parameter | Description
--------- | -----------
order_id | The order ID displayed in reports and printed on receipts
transaction_id | The order ID used for the subsequent payment effect
date_open | Time of order creation in the timestamp format with milliseconds
payed_sum | The amount for a visitor to pay for the order (in hryvnias/rubles)
products | List of products ordered by a visitor. Each element of the array contains the product name in the form of the product_name property, and can also contain a modificator_name property if it is a product modification.

