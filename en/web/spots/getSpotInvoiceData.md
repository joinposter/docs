## spots.getSpotInvoiceData: Get location invoice data

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/spots.getSpotInvoiceData'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&spot_id=1';

$data = PosterAPI::sendRequest($url);
```

> Response example:

```json
{
    "response":{
       "invoice_name":"Friends Cafe",
       "invoice_id":12,
       "invoice_address":"1st Street, apt 89"
    }
 }

```

Method returns location invoice data

### HTTP request

`GET https://joinposter.com/api/spots.getSpotInvoiceData`

### Request GET-params for spots.getSpotInvoiceData

Parameter | Description
--------- | -----------
spot_id | Location ID

### Response from spots.getSpotInvoiceData

Parameter | Description
--------- | -----------
response | Response result object

`response` contains object with next params:

Parameter | Description
--------- | -----------
invoice_name | Location name
invoice_id | Invoice id
invoice_address | Location address  
