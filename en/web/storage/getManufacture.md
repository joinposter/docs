## storage.getManufacture: Manufacture Data

> Request example:

```php
<?
$url = 'https://joinposter.com/api/storage.getManufacture' 
  . '?format=json'
  . '&token=687409:4164553abf6a031302898da7800b59fb'
  . '&manufacture_id=4';

$data = sendRequest($url);
```
> Response example:

```json
{
  "response":{
    "manufacture_id":"4",
    "storage_name":"Storage 1",
    "storage_id":"1",
    "user_id":"4",
    "date":"2016-12-26 14:45:00",
    "sum":70.35,
    "sum_netto":58.63,
    "products":[
      {
        "ingredient_id":"205",
        "product_id":"134",
        "product_name":"Flower tea 360ml",
        "product_num":"3.0000",
        "type":"2"
      },
      {
        "ingredient_id":"204",
        "product_id":"137",
        "product_name":"Black tea",
        "product_num":"2.0000",
        "type":"2"
      }
    ]
  }
}
```

The request returns the data of a particular manufacture.

### HTTP request

`GET https://joinposter.com/api/storage.getManufacture`

### GET parameters of the storage.getManufacture request

Parameter | Description
--------- | -----------
manufacture_id | The ID of a manufacture to return detailed data to

### The storage.getManufacture response parameters

Parameter | Description
--------- | -----------
manufacture_id | Manufacture ID
storage_name | Storage name
storage_id | Storage ID
user_id | The ID of the user who has manufactured
date | Manufacture date
sum | The total amount of manufacture in hryvnias/rubles
sum_netto | The total amount of manufacture without VAT in hryvnias/rubles. Is returned if the 'Calculate cost and net profit' setting is enabled
products | List of dishes / semi-finished products included in the manufacture

### The products parameter entry

The word “entity” means a dish or a semi-finished product. When the entity is manufactured for the first time, it gets a unique ingredient_id to get its inventory in storage by.

Parameter | Description
--------- | -----------
ingredient_id | A unique ingredient_id of the entity
product_id | Entity ID
product_name | Entity name
product_num | Count in pieces, kg, or liters
type | Type of entity: 1—semi-finished product, 2—dish

