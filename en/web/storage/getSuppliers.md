## storage.getSuppliers: Get all Suppliers

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/storage.getSuppliers'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);
```

> Response example:

```json
{
  "response":[
    {
      "supplier_id":"1",
      "supplier_name":"Закупщик",
      "supplier_phone":"+7 499 555 55 55",
      "supplier_adress":"",
      "supplier_comment":"",
      "supplier_code":"",
      "supplier_tin":"",
      "delete":"0"
    },
    {
      "supplier_id":"2",
      "supplier_name":"Напитков Иван",
      "supplier_phone":"0956734678",
      "supplier_adress":"ул. Лесная 3",
      "supplier_comment":"",
      "supplier_code":"",
      "supplier_tin":"",
      "delete":"0"
    },
    {
      "supplier_id":"3",
      "supplier_name":"Овощной Иван",
      "supplier_phone":"0987658943",
      "supplier_adress":"ул. Байкальская",
      "supplier_comment":"",
      "supplier_code":"",
      "supplier_tin":"",
      "delete":"0"
    }
  ]
}
```

The method returns all suppliers

### HTTP request

`GET https://joinposter.com/api/storage.getSuppliers`

### GET parameters of the storage.getSuppliers request

Parameter | Description
--------- | -----------
id_1c | An optional parameter; `true` if id_1 is returned

### The storage.getSuppliers response parameters

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an array, each element of which contains the following parameters:

Parameter | Description
--------- | -----------
supplier_id | Supplier ID
supplier_name | Supplier name
supplier_phone | Supplier phone number
supplier_adress | Supplier address
supplier_comment | Comment
supplier_code | Unique Identification Number of a legal entity
supplier_tin | Supplier TIN
delete | The status of a supplier removed: 1—removed, 0—not removed

