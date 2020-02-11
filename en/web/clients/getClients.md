## clients.getClients: List of Customers

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/clients.getClients'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&num=100'
 . '&offset=0';

$data = sendRequest($url);
```

> Response example:

```json
{  
  "response":[  
    {  
      "client_id":"55",
      "firstname":"",
      "lastname":"Антон",
      "patronymic":"",
      "discount_per":"0",
      "bonus":"10000",
      "total_payed_sum":"0",
      "date_activale":"2017-10-09 15:28:14",
      "phone":"+7 963 031-38-44",
      "phone_number":"79630313844",
      "email":"bezmuki@gmail.com",
      "birthday":"0000-00-00",
      "card_number":"0",
      "client_sex":"0",
      "country":"0",
      "city":"0",
      "comment":"0",
      "address":"0",
      "client_groups_id":"3",
      "client_groups_name":"Накопительная скидка",
      "client_groups_discount":"0",
      "loyalty_type":"1",
      "birthday_bonus":"0",
      "delete":"0",
      "ewallet": "0"
    },
    {  
      "client_id":"54",
      "firstname":"",
      "lastname":"Вася",
      "patronymic":"",
      "discount_per":"0",
      "bonus":"10000",
      "total_payed_sum":"0",
      "date_activale":"2017-10-09 11:39:59",
      "phone":"+7 977 345-34-45",
      "phone_number":"79773453445",
      "email":"sdfs@ffy.hu",
      "birthday":"0000-00-00",
      "card_number":"0",
      "client_sex":"0",
      "country":"0",
      "city":"0",
      "comment":"0",
      "address":"0",
      "client_groups_id":"2",
      "client_groups_name":"Скидка Выходной",
      "client_groups_discount":"15",
      "loyalty_type":"1",
      "birthday_bonus":"0",
      "delete":"0",
      "ewallet": "0"
    }
  ]
}
```

The method returns a list of customers

### HTTP request

`GET https://joinposter.com/api/clients.getClients`

### GET parameters of the clients.getClients request

Parameter | Description
--------- | -----------
num | Customer count to receive. By default, it is not transmitted.
offset | Customer count to skip from the beginning. By default, it is not transmitted.
group_id | Customer group ID. By default, it is not transmitted.
phone | Customer phone number in an international format. By default, it is not transmitted.
birthday | Customers date of birth in an “md” format. By default, it is not transmitted.
client_id_only | An optional parameter; it allows returning customers’ client_id only. The value must be specified as true.
1c | It allows returning the customer ID in the 1C system in the response. You must transmit true as a value. By default, it is not transmitted.
order_by | A property to sort by. By default, it takes `client_id`.
sort | Sorting order: `asc`—ascending, `desc`—descending. The default value is `desc`.

!> If num and offset are not specified, all customers will be returned without a pagination
### The clients.getClients response parameters

Parameter | Description
--------- | -----------
response | An array of objects

Inside the `response` parameter, there is an array, each element of which contains the following parameters:

Parameter | Description
--------- | -----------
client_id | Customer ID
firstname | Customer first name
lastname | Customer last name
patronymic | Customer patronymic
discount_per | Personal discount or point. It will be applied if it is higher than a customer group percentage.
bonus | The current amount of accumulated customer points in kopecks
total_payed_sum | Total purchase sum in kopecks
date_activale | Date of customer creation
phone | Customer phone number
phone_number | Customer phone number in a digital format
email | Customer email address
birthday | Customer date of birth
card_number | Card number
client_sex | Customer gender: 0—not specified, 1—male, 2—female
country | Customer country
city | Customer city
address | Customer address
comment | Customer account comment
id_1c | Customer ID in the 1C system
client_groups_id | Customer group ID
client_groups_name | Customer group name
loyalty_type | Customer group type: 1—points-based, 2—discount-based
client_groups_discount | Group percentage. If it is a points-based group—1, points will be accrued to the paid order amount. If it is a discount-based group—1, discount percentage will be accrued to the order amount.
birthday_bonus | The points count in kopecks accrued on the customer’s birthday. It is used only by points-based groups.
delete | Delete: 0 — No, 1 — Yes
ewallet | Electronic wallet balance in cents
