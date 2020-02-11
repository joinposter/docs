## incomingOrders.createReservation: Create Reservation

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/incomingOrders.createReservation'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$reservation = [
    'spot_id'           => '1',
    'phone'             => '+380684112224',
    'table_id'          => '1',
    'guests_count'      => '1',
    'duration'          => '2000',
    'date_reservation'  => '2018-03-22 16:20:00'
];

$data = sendRequest($url, 'post', $reservation);

```

> Response example:

```json
{
   "response":{
      "incoming_order_id":"4",
      "type":"2",
      "spot_id":"1",
      "status":0,
      "client_id":4985,
      "first_name":"Владимир",
      "last_name":"Иванов",
      "phone":"380684112224",
      "email":"example@gmail.com",
      "sex":"2",
      "birthday":"1996-08-26",
      "address":"",
      "guests_count":"1",
      "comment":"",
      "created_at":"2018-03-22 17:02:41",
      "updated_at":"2018-03-22 17:02:41",
      "transaction_id":null,
      "fiscal_spreading":"0",
      "fiscal_method":"",
      "promotion":null,
      "date_reservation":"2018-03-22 18:20:00",
      "duration":"2000"
   }
}
```

The method creates a table reservation for the specified time and customer

### HTTP POST request

`POST https://joinposter.com/api/incomingOrders.createReservation`

### POST parameters of the incomingOrders.createReservation request

Parameter | Description
--------- | -----------
spot_id | A mandatory parameter, the location ID the online order will come to
type | Order type: 1—online order, 2—reservation
table_id | A mandatory parameter, the ID of the table reserved
date_reservation | A mandatory parameter, the reservation start date in the `Y-m-d H:i:s` format
duration | A mandatory parameter, the reservation duration in seconds. Must be at least 1800 seconds (half an hour).
client_id | The customer ID in Poster; by default, it is not transmitted. In case the ID is not specified, Poster will try to find a customer with the same phone number and attach him to the order. If it is a new customer, the waiter will select a group for him, and Poster will create a new customer.
phone | The customer’s phone number; by default, it is not transmitted
first_name | The customer’s name; by default, it is not transmitted.
last_name | The customer’s last name; by default, it is not transmitted.
email | Email; is not transmitted by default
sex | Customer gender: 0—not specified, 1—male, 2—female. By default, it is not transmitted.
birthday | Customer’s birthday in a `Y-m-d` format. By default, it is not transmitted.
address | Customer’s address; by default, it is not transmitted
comment | Reservation comment; it is not transmitted by default

### incomingOrders.createReservation response parameters

Parameter | Description
--------- | -----------
response | Response object

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
comment | Online order comment
created_at | Online order creation date
updated_at | Online order status update date
date_reservation | The reservation start date in the `Y-m-d H:i:s` format
duration | Reservation duration in seconds

