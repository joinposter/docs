## finance.getCategories: Get an Account Category List

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/finance.getCategories'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);
```

> Response example:

```json
{
  "response":[
    {
      "category_id":"5",
      "name":"Зарплата",
      "parent_id":"0",
      "operations":"2",
      "action":"0",
      "delete":"0"
    },
    {
      "category_id":"2",
      "name":"Кассовые смены",
      "parent_id":"0",
      "operations":"3",
      "action":"11",
      "delete":"0"
    }
  ]
}
```

The method of getting a list of financial account categories

### HTTP request

`GET https://joinposter.com/api/finance.getCategories`

### The finance.getCategories response parameters

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an array of objects with the following parameters inside each of them:

Parameter | Description
--------- | -----------
category_id | Category ID
name | Category name
parent_id | Subcategory ID
operation | Valid transactions: 1—income, 2—expenditure, 3—income and expenditure, 0—not selected
action | Type of categories by operations: 1—transfers, 11—register shifts, 12—supplies, 14—adjustment, 0—any type of operation

