## access.createEmployee: Create an Employee

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/access.createEmployee'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$employee = [
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
  "response":15
}
```

The method creates an employee

All employees have their own roles and access rights:

- Waiter—no access to the management console
- Floor section administrator—order management at the register
- Marketer—access to reports and marketing tools
- Storekeeper—access to storages and supplies

### HTTP POST request

`https://joinposter.com/api/access.createEmployee`

### POST parameters of the access.createEmployee request

Parameter | Description
--------- | -----------
name | Employee first and last name
user_type | The employee role: 0—waiter, 2—marketer, 3—storekeeper, 4—floor section administrator
pos_pass | Pin code of the location waiter or administrator for authorization in the register
login | Employee login for access to the management system; it is needed for a marketer and storekeeper only
pass | Employee password to access the management system; it is needed for a marketer and storekeeper only
inn | Employee ITIN which will be sent to the fiscal registrar. Needed for customers from Russia with enabled fiscalization only.
name_for_fiscal | Employee full name which will be sent to the fiscal registrar. Needed for customers from Russia with enabled fiscalization only.

### The access.createEmployee response parameters

Parameter | Description
--------- | -----------
response | The created employee ID

