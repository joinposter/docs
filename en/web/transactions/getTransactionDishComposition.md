## transactions.getTransactionDishComposition: The Sold Dish Recipe

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/transactions.getTransactionDishComposition'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&transaction_id=76'
 . '&product_id=82'
 . '&modificator_id=22';

$data = sendRequest($url);
```

> Response example:

```json
{  
  "response":{  
    "transaction_id":76,
    "product_id":82,
    "modificator_id":22,
    "num":1,
    "ingredients":[  
      {  
        "ingredient_id":135,
        "type":1,
        "weight":0.6
      },
      {  
        "ingredient_id":24,
        "type":2,
        "weight":0.05
      },
      {  
        "ingredient_id":136,
        "type":1,
        "weight":2
      }
    ]
  }
}
```

The method returns the recipe of the dish sold

### HTTP GET request

`https://joinposter.com/api/transactions.getTransactionDishComposition`

### GET parameters of the transactions.getTransactionDishComposition request

Parameter | Description
--------- | -----------
transaction_id | Order ID
product_id | Dish ID
modificator_id | Modifier ID; by default, it is 0

### Parameters of the transactions.getTransactionDishComposition request

Inside the `response` parameter, there is an object containing the following parameters:

Parameter | Description
--------- | -----------
transaction_id | Order ID
product_id | Dish ID
modificator_id | Modifier ID
num | Dish count in the order
ingredients | Dish receipt at the time of sale

Inside the `ingredients` parameter, there is an object with the following parameter:

Parameter | Description
--------- | -----------
ingredient_id | Ingredient ID
type | Type: 1—ingredient, 2—semi-finished product
weight | Count

