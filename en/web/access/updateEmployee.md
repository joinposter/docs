## access.updateEmployee: Update Employee Properties

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/access.updateEmployee'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$employee = [
    'user_id'   => 15,
    'name'      => 'John Doe',
    'user_type' => 2,
    'pos_pass'  => '',
    'login'     => 'john.doe@test.com',
    'pass'      => 'aZntaeVP9h',
];

$data = sendRequest($url, 'post', $employee);
```

> Response example:

```json
{
  "response":4082
}
```

The method updates an employee properties

All employees have their own roles and access rights:

- Waiter—no access to the management console
- Floor section administrator—order management at the register
- Marketer—access to reports and marketing tools
- Storekeeper—access to storages and supplies

### HTTP POST request

`https://joinposter.com/api/access.updateEmployee`

### POST parameters of the access.updateEmployee request

Parameter | Description
--------- | -----------
user_id | Employee ID
name | Employee first and last name
user_type | The employee role: 0—waiter, 2—marketer, 3—storekeeper, 4—floor section administrator
pos_pass | Pin code of the location waiter or administrator for authorization in the register
login | Employee login for access to the management system; it is needed for a marketer and storekeeper only
pass | Employee password to access the management system; it is needed for a marketer and storekeeper only
inn | Employee ITIN which will be sent to the fiscal registrar. Needed for customers from Russia with enabled fiscalization only.
name_for_fiscal | Employee full name which will be sent to the fiscal registrar. Needed for customers from Russia with enabled fiscalization only.

### The access.updateEmployee response parameters

Parameter | Description
--------- | -----------
response | The updated employee ID

