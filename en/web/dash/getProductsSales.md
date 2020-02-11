## dash.getProductsSales: Product Sales

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/dash.getProductsSales'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);
```

> Response example:

```json
{
  "response":[
    {
      "product_name":"Стейк из сёмги",
      "modificator_name":null,
      "product_id":"168",
      "modification_id":"0",
      "delete":"0",
      "left":"43",
      "right":"44",
      "category_id":"33",
      "count":"171.0000",
      "weight_flag":"0",
      "payed_sum":"7650000",
      "product_sum":"7695000",
      "bonus_sum":"0",
      "cert_sum":"45000",
      "product_profit":"7199716",
      "product_profit_netto":"5999763",
      "tax_sum":"72000",
      "vat_sum":"0",
      "unit":"p",
      "discount":45000
    },
    {
      "product_name":"Речная форель в фольге",
      "modificator_name":null,
      "product_id":"169",
      "modification_id":"0",
      "delete":"0",
      "left":"43",
      "right":"44",
      "category_id":"33",
      "count":"168.0000",
      "weight_flag":"0",
      "payed_sum":"9185000",
      "product_sum":"9240000",
      "bonus_sum":"0",
      "cert_sum":"55000",
      "product_profit":"8367880",
      "product_profit_netto":"6973233",
      "tax_sum":"88000",
      "vat_sum":"0",
      "unit":"p",
      "discount":55000
    }
  ]
}
```

The method returns product sales

### HTTP request

`GET https://joinposter.com/api/dash.getProductsSales`

### GET parameters of the dash.getProductsSales request

Parameter | Description
--------- | -----------
spot_id | An optional parameter, the ID of a location to return reports to
date_from | An optional parameter, the sampling start date in the `Ymd` format, inclusive. The default date is a month ago.
date_to | An optional parameter, the sampling end date in the `Ymd` format, inclusive. The default date is the current date.

### Parameters of the dash.getProductsSales response

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an array of objects. Each object contains the following parameters:

Parameter | Description
--------- | -----------
product_name | Product name
product_id | Product ID
modification_id | Modifier ID; if the product is without a modifier, it’s 0
modification_name | The modifier name; `null` if the product is without a modifier
category_id | Product category ID
left | Left category ID
right | Right category ID
price | Product cost
count | Sold products count
weight_flag | The status of a product sold by weight, 0—not sold by weight, 1—sold by weight
payed_sum | The amount paid by hard cash including discount; equals `payed_cash` + `payed_card`
product_sum | Price in kopecks
product_profit | Profit in kopecks
product_profit_netto | Profit without VAT in kopecks. Is returned if the 'Calculate cost and net profit' setting is enabled
discount | Discount amount in kopecks
delete | The status of a product removed: 0—not removed, 1—removed
