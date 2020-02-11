## clients.getClient: Customer Properties

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/clients.getClient'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&client_id=6';

$data = sendRequest($url);
```

> Response example:

```json
{
  "response":[
    {
      "client_id":"38",
      "firstname":"Попова",
      "lastname":"000022",
      "patronymic":"Елена",
      "discount_per":"0",
      "bonus":"0",
      "total_payed_sum":"417000",
      "date_activale":"2016-04-23 05:14:26",
      "phone":"+380 50 11-11-111",
      "phone_number":"380501111111",
      "email":"contact@joinposter.com",
      "birthday":"1986-11-23",
      "card_number":"0000000000222",
      "client_sex":"0",
      "country":"",
      "city":"",
      "comment":"",
      "address":"",
      "client_groups_id":"7",
      "client_groups_name":"Постоянный клиент",
      "client_groups_discount":"0",
      "loyalty_type":"2",
      "birthday_bonus":"0",
      "accumulation_products":{
        "4":{
          "promotion_id":"4",
          "products":[
            {
              "count":"3",
              "sum":540,
              "product_id":"24",
              "modification_id":"0"
            }
          ]
        }
      },
      "prize_products":[
        {
          "prize_product_id":"301",
          "promotion_id":"4",
          "conditions":{
            "bonus_products":[
              {
                "type":"1",
                "id":"1"
              }
            ],
            "bonus_products_pcs":1,
            "bonus_products_g":0,
            "bonus_products_condition_type":"1",
            "bonus_products_condition_value":"100"
          },
          "date_accrual":"2016-05-11 11:40:10"
        }
      ],
      "ewallet": "1000"
    }
  ]
}
```

The method returns the customer properties

### HTTP request

`GET https://joinposter.com/api/clients.getClient`

### GET parameters of the clients.getClient request

Parameter | Description
--------- | -----------
client_id | Customer ID
1c | It allows returning the customer ID in the 1C system in the response. You must transmit true as a value. By default, it is not transmitted.

### The clients.getClient response parameters

Parameter | Description
--------- | -----------
response | An array of objects

Inside the `response` parameter, there is an array with an object, each element of which contains the following parameters:

Parameter | Description
--------- | -----------
client_id | Customer ID
firstname | Customer first name
lastname | Customer last name
patronymic | Customer patronymic
discount_per | Personal discount or point. It will be applied if it is higher than a customer group percentage.
bonus | The current amount of accumulated customer points in kopecks
total_payed_sum | Total purchase sum in kopecks
date_activale | Date of customer creation
phone | Customer phone number
phone_number | Customer phone number in a digital format
email | Customer email address
birthday | Customer date of birth
card_number | Card number
client_sex | Customer gender: 0—not specified, 1—male, 2—female
country | Customer country
city | Customer city
address | Customer address
comment | Customer account comment
id_1c | Customer ID in the 1C system
client_groups_id | Customer group ID
client_groups_name | Customer group name
loyalty_type | Customer group type: 1—points-based, 2—discount-based
client_groups_discount | Group percentage. If it is a points-based group—1, points will be accrued to the paid order amount. If it is a discount-based group—2, discount percentage will be accrued to the order amount.
birthday_bonus | The points count in kopecks accrued on the customer’s birthday. It is used only by points-based groups.
accumulation_products | List of sales relating to accumulation-based promotions. For example, a “5+1” promotion, which takes into account purchases in different orders.
prize_products | List of deferred points, which are related to prize promotions. For example, a “Buy a Pizza and Get a 10% Cheaper One Tomorrow” promotion meaning prizes that are not granted immediately but are postponed to the next purchase.
ewallet | Electronic wallet balance in cents

The `accumulation_products` parameter contains the object:

Parameter | Description
--------- | -----------
promotion_id | The accumulation-based promotion ID the sale is attached to
products | List of products of a sale transaction completed relating to the accumulation-based promotion. The content of this array of products is described below.
product_id | Product ID
modification_id | Modification ID if a product has modifications
count | Product count
sum | Product cost

The `prize_products` parameter contains the object:

Parameter | Description
--------- | -----------
prize_product_id | The deferred prize unique ID
promotion_id | Prize promotion ID
conditions | List of conditions for determining the prize that has to be granted, type designates: 0—of all products, 1—of the category indicated in the ID, 2—specific product with the specified ID, 3—product modification with the specified ID (for convenience, the product_id of the product the modification is related to will be transferred)
bonus_products_pcs | The number of points-based product pieces to grant if it is sold by the piece
bonus_products_g | The points-based product grams to grant if it is sold by weight
bonus_products_condition_type | The conditions for granting points: 1—discount percentage (for example, a 50 or 100% discount), 2—a fixed discount amount (for example, 5-hryvnia/ruble discount on the product), 3—fixed product value (for example, sell at 1 hryvnia/ruble)
bonus_products_condition_value | The count for the bonus_products_condition_type parameter. If the value is monetary, the return is in hryvnias/rubles.

