## transactions.getTransactionsWriteOffs: Order Wastes

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/transactions.getTransactionsWriteOffs'
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
        "write_offs":[  
          {  
            "write_off_id":143731,
            "storage_id":3,
            "product_id":469,
            "modificator_id":0,
            "ingredient_id":30,
            "prepack_id":0,
            "cost":26.68,
            "cost_netto":22.23,
            "weight":0.16,
            "unit":"kg",
            "reason":""
          }
        ]
      }
    ]
  }
}
```

The method returns the order wastes in the date range and pagination

### HTTP GET request

`https://joinposter.com/api/transactions.getTransactionsWriteOffs`

### GET parameters of the transactions.getTransactionsWriteOffs request

Parameter | Description
--------- | -----------
date_from | Sampling start date in the “Y-m-d” format
date_to | Sampling end date in the “Y-m-d” format
per_page | Orders count on one page. By default, it takes 100; the maximum value is 1000.
page | Page number, the default number is 1

### The transactions.getTransactionsWriteOffs response parameters

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
write_offs | Order wastes

Inside the `write_offs` parameter, there is an array, each element of which contains the following parameters:

Parameter | Description
--------- | -----------
write_off_id | Waste ID
storage_id | ID of the storage where the waste occurred
product_id | Product ID
modificator_id | Modifier ID
ingredient_id | Ingredient ID For manufactured dishes and semi-finished components, there will be returned the [entity’s ingredient system ID](/en/docs/v3/web/storage/getManufacture)
prepack_id | Semi-finished product ID
cost | Cost
cost_netto | Cost without VAT
weight | Count
unit | Unit: kg—kilograms, p—pieces, l—liters
reason | Waste reason

<aside class="info">
Note:
“prepack_id” returns the value only if the semi-finished product has been manufactured.
Otherwise, “ingredient_id” / “prepack_id” the semi-finished product consists of will be returned.
</aside>
