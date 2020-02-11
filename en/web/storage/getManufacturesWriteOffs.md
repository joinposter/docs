## storage.getManufacturesWriteOffs: Manufacture Wastes

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/storage.getManufacturesWriteOffs'
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
    "count":11,
    "page":{  
      "per_page":10,
      "page":2,
      "count":1
    },
    "data":[  
      {  
        "manufacture_id":15,
        "storage_id":2,
        "date":"2017-11-30 15:00:00",
        "products":[  
          {  
            "product_id":105,
            "type":2,
            "num":10,
            "sum":123.45,
            "sum_netto":102.88,
            "is_fiscal":0,
            "write_offs":[  
              {  
                "ingredient_id":165,
                "type":1,
                "weight":123.45
              }
            ]
          }
        ]
      }
    ]
  }
}
```

The method returns the manufacture wastes in the date range and pagination

### HTTP GET request

`https://joinposter.com/api/storage.getManufacturesWriteOffs`

### GET parameters of the storage.getManufacturesWriteOffs request

Parameter | Description
--------- | -----------
date_from | Sampling start date in the “Y-m-d” format
date_to | Sampling end date in the “Y-m-d” format
per_page | Orders count on one page. By default, it takes 100; the maximum value is 1000.
page | Page number, the default number is 1

### The storage.getManufacturesWriteOffs response parameters

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
manufacture_id | Manufacture ID
storage_id | Storage ID
date | Manufacture date
products | Manufactured semi-finished products and dishes

The `products` parameter has an array inside, each element of which contains the following parameters:

Parameter | Description
--------- | -----------
product_id | The ID of a semi-finished product or dish
type | Type: 1—semi-finished product, 2—dish
num | Count
sum | The total amount for all quantity
sum_netto | The total amount without VAT for all quantity. Is returned if the 'Calculate cost and net profit' setting is enabled
is_fiscal | Tha status of fiscality: 0—non-fiscal, 1—fiscal
write_offs | Wastes list

Inside the `write_offs` parameter, there is an array, each element of which contains the following parameters:

Parameter | Description
--------- | -----------
ingredient_id | Ingredient ID
type | Type: 1—ingredient, 2—semi-finished product
weight | Total amount
