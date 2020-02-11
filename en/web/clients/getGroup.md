## clients.getGroup: Customer Group Properties

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/clients.getGroup'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&group_id=2';

$data = sendRequest($url);
```

> Response example:

```json
{  
  "response":{  
    "client_groups_id":"2",
    "client_groups_name":"Скидка Выходной",
    "client_groups_discount":"15",
    "loyalty_type":"1",
    "birthday_bonus":"0",
    "count_groups_clients":"21",
    "delete":"0"
  }
}
```

The method returns the customer group properties

### HTTP request

`GET https://joinposter.com/api/clients.getGroup`

### GET parameters of the clients.getGroup request

Parameter | Description
--------- | -----------
group_id | Customer group ID

### The clients.getGroup response parameters

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an object containing the following parameters:

Parameter | Description
--------- | -----------
client_groups_id | Customer group ID
client_groups_name | Customer group name
client_groups_discount | Group percentage. If it is a points-based group—1, points will be accrued to the paid order amount. If it is a discount-based group—2, discount percentage will be accrued to the order amount.
loyalty_type | Customer group type: 1—a points-based one, 2—discount-based
birthday_bonus | The points count in kopecks accrued on the customer’s birthday. It is used only by points-based groups.
count_groups_clients | Number of customers who are in this group
use_ewallet | Indication for using e-Wallets in a customer group: 0 — not to use, 1 — to use.
delete | Determines whether the group has been removed: 1—removed, 0—not

