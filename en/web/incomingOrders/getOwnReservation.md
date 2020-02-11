## incomingOrders.getOwnReservation: Reservation Properties from your Application

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/incomingOrders.getOwnReservation'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&incoming_order_id=3';

$data = sendRequest($url);

```

> Response example:

```json
{
   "response":{
      "incoming_order_id":"3",
      "spot_id":"1",
      "status":0,
      "client_id":4985,
      "first_name":"Степан",
      "last_name":"Созонов",
      "phone":"380912152764",
      "email":null,
      "sex":"2",
      "birthday":"1996-08-26",
      "address":"московская 9",
      "comment":"Подготовить вазу для цветов",
      "created_at":"2018-03-22 16:50:18",
      "updated_at":"2018-03-22 16:50:18",
      "transaction_id":null,
      "guests_count":"1",
      "duration":"2000",
      "date_reservation":"2018-03-22 18:20:00"
   }
}
```

The method returns the reservation properties

### HTTP GET request

`GET https://joinposter.com/api/incomingOrders.getOwnReservation`

### GET parameters of the incomingOrders.getOwnReservation request

Parameter | Description
--------- | -----------
incoming_order_id | Reservation ID

### incomingOrders.getOwnReservation response parameters

Parameter | Description
--------- | -----------
response | An array of objects

Inside the `response` parameter, there is an object containing the following parameters:

Parameter | Description
--------- | -----------
incoming_order_id | Reservation ID
type | Order type: 1—online order, 2—reservation. For this method, it always equals 2.
spot_id | Location ID
status | Reservation status: 0—new, 1—accepted, 7—canceled
client_id | Customer ID
first_name | Customer first name
last_name | Customer last name
phone | Customer phone number
email | Customer’s email
sex | Customer gender: 0—not specified, 1—male, 2—female
birthday | Customer’s birthday in a `Y-m-d` format
address | Customer address
comment | Reservation comment
created_at | Reservation creation date
updated_at | Reservation update date
date_reservation | The reservation start date in the `Y-m-d H:i:s` format
duration | Reservation duration in seconds

