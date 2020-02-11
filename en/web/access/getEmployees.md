## access.getEmployees: Employee List

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/access.getEmployees'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);
```

> Response example:

```json
{
  "response":[
    {
      "user_id":3,
      "name":"Semen Tick",
      "user_type":90,
      "role_id": 1,
      "role_name": "Marketer",
      "access_mask": 34,
      "last_in":"2017-03-07 13:03:47"
    },
    {
      "user_id":9,
      "name":"John Doe",
      "user_type":0,
      "role_id": 2,
      "role_name": "Waiter",
      "access_mask": 1,
      "last_in":"2017-03-07 14:03:03"
    }
  ]
}
```

The method returns a list of employees

### HTTP GET request

`https://joinposter.com/api/access.getEmployees`

### The access.getEmployees response parameters

Parameter | Description
--------- | -----------
response | An array of objects

Inside the `response` parameter, there is an array, each element of which contains the following parameters:

Parameter | Description
--------- | -----------
user_id | Employee ID
name | Employee first and last name
role_id | User position ID
role_name | Position name
access_mask | [Bit mask](https://en.wikipedia.org/wiki/Mask_(computing\)) which contains information about employee access for each section in Poster. See bytes explanation in the table below.
user_type | The employee role: 0 — waiter, 1 — administrator, 2 — marketer, 3 — storekeeper, 4 — floor section administrator, 50 — manager, 90 — owner
last_in | Date of the last login to the management console
inn | Employee ITIN which will be sent to the fiscal registrar. Shown to customers from Russia with enabled fiscalization only.
name_for_fiscal | Employee full name which will be sent to the fiscal registrar. Shown to customers from Russia with enabled fiscalization only.


All employees have their own positions and access rights. By default Poster has such roles:

* Waiter — no access to the management console
* Floor section administrator — order management at the register
* Marketer — access to reports and marketing tools
* Storekeeper — access to storages and supplies

But the user can customize the default or create new roles.
So to check if a user has access to the particular section, use bitwise “AND” (&) with `access_mask` field and following bytes:


Byte | Poster Section
---- | --------------
1 | POS
2 | Reports
4 | Finance
8 | Products
16 | Inventory
32 | Marketing
64 | Access
128 | Settings
256 | Floor section administrator
512 | Security
