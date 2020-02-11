## clients.createGroup: Create a Customer Group

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/clients.createGroup'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$group = [
    'client_groups_name'     => 'Постоянный посетитель',
    'loyalty_type'           => 1,
    'client_groups_discount' => 10,
    'birthday_bonus'         => 50.00,
];

$data = sendRequest($url, 'post', $group);
```

> Response example:

```json
{
  "response":6
}
```

The method creates a customer group

### HTTP request

`POST https://joinposter.com/api/clients.createGroup`

### POST parameters of the clients.createGroup request

Parameter | Description
--------- | -----------
client_groups_name | Customer group name
loyalty_type | Customer group type: 1—a points-based one, 2—discount-based
client_groups_discount | Group percentage. If it is a points-based group—1, points will be accrued to the paid order amount. If it is a discount-based group—2, discount percentage will be accrued to the order amount.
birthday_bonus | The points count in kopecks accrued on the customer’s birthday. It is used only by points-based groups.
use_ewallet | Indication for using e-Wallets in a customer group: 0 — not to use, 1 — to use

### The clients.createGroup response parameters

Parameter | Description
--------- | -----------
response | Created customer group ID

