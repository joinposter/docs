## storage.createSupplier: Create a Supplier

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/storage.createSupplier'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$supplier = [
    'supplier_name'    => 'Валера',
    'supplier_adress'  => 'пр. Петровского',
    'supplier_phone'   => 380671234567,
    'supplier_code'    => 32855961,
    'supplier_tin'     => 6449013711,
    'supplier_comment' => 'Мясо',
];

$data = sendRequest($url, 'post', $supplier);
```

> Response example:

```json
{  
  "response":6
}
```

The method creates a supplier

### HTTP POST request

`https://joinposter.com/api/storage.createSupplier`

### POST parameters of the storage.createSupplier request

Parameter | Description
--------- | -----------
supplier_name | Supplier name
supplier_adress | Address
supplier_phone | Phone number
supplier_code | EDRPOU
supplier_tin | TIN
supplier_comment | Comment

### The storage.createSupplier response parameters

Parameter | Description
--------- | -----------
response | The created supplier ID

