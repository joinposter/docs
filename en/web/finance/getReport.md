## finance.getReport: Category Report

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/finance.getReport'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);
```

> Response example:

```json
{
  "response":{
    "periods":[
      {
        "title":"Oct 2017",
        "start":1508101200,
        "end":1509483599
      },
      {
        "title":"Nov 2017",
        "start":1509483600,
        "end":1510865999
      }
    ],
    "categories":{
      "7":{
        "category_id":"7",
        "name":"book_category_action_actualization",
        "parent_id":"0",
        "operations":"3",
        "action":"14",
        "level":"1",
        "left":"1",
        "right":"2",
        "delete":"0",
        "amounts": {
          "1":{
            "Nov 2017":200000
          }
        },
        "currency_symbol":"<i class=\"icon-rouble\"><\/i>"
      },
      "8":{
        "category_id":"8",
        "name":"book_category_action_banking_services",
        "parent_id":"0",
        "operations":"3",
        "action":"15",
        "level":"1",
        "left":"3",
        "right":"4",
        "delete":"0"
      }
    }
  }
}
```

The method returns a category report

### HTTP request

`GET https://joinposter.com/api/finance.getReport`

### GET parameters of the finance.getReport request

Parameter | Description
--------- | -----------
dateFrom | An optional parameter, the sampling start date in the `Ymd` format, inclusive. The default date is a month ago.
dateTo | An optional parameter, the sampling end date in the `Ymd` format, inclusive. The default date is the current date.
account_id | An optional parameter, the account ID to return a report to. The default value is to all.
period | An optional parameter, the sampling period: 1—by years, 2—by quarters, 3—by months, 4—by weeks, 5—by days. The default value is 3—by months.

### The finance.getReport response parameters

Parameter | Description
--------- | -----------
response | Response object

Inside the `response` parameter, there is an object containing the following parameters:

Parameter | Description
--------- | -----------
periods | The array contains the periods the report is structured by
categories | An object with a category ID as properties and a report object as a value

The `periods` array objects have the following properties

Parameter | Description
--------- | -----------
title | Period name: year, quarter, month, week, day
start | Period start date in the unixtimestamp format
end | Period end date in the unixtimestamp format

Each property of the `categories` object contains the following parameters

Parameter | Description
--------- | -----------
category_id | Category ID
name | Category name
delete | The status of the category having been removed: 1—removed, 0—not removed
parent_id | Parent category ID
operations | Transactions count performed in the category for the selected period
action | Type of categories by operations: 1—transfers, 11—register shifts, 12—supplies, 14—adjustment, 0—any type of operation
left | The ID of the left category (by the Nested Set)
right | The ID of the right category (by the Nested Set)
level | Level of nesting of the category tree branch (by the Nested Set)
currency_symbol | Unicode currency symbol; for the ruble, dram, and manat, HTML comes displayed on the register as a currency icon
amounts | Total costs and revenues in a category. Contains a set of objects. Each object has a `periods.title` period name as a property and the amount in kopecks for a given period as a value.

