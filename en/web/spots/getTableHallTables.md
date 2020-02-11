## spots.getTableHallTables: Table List

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/spots.getTableHallTables'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&spot_id=1'
 . '&hall_id=3'
 . '&without_deleted=1';

$data = sendRequest($url);
```

> Response example:

```json
{  
  "response":[  
    {  
      "table_id":"3",
      "table_num":"1",
      "table_title":"Возле барной стойки",
      "spot_id":"1",
      "table_shape":"square",
      "hall_id":"1",
      "table_x":"9",
      "table_y":"12",
      "table_height":"4",
      "table_width":"8",
      "is_deleted":"0",
      "status":"1"
    },
    {  
      "table_id":"4",
      "table_num":"2",
      "table_title":"Дальний",
      "spot_id":"1",
      "table_shape":"circle",
      "hall_id":"1",
      "table_x":"15",
      "table_y":"11",
      "table_height":"10",
      "table_width":"13",
      "is_deleted":"0",
      "status":"2"
    }
  ]
}
```

The method returns the list of tables

### HTTP request

`GET https://joinposter.com/api/spots.getTableHallTables`

### GET parameters of the spots.getTableHallTables request

Parameter | Description
--------- | -----------
spot_id | Location ID; by default, it is not transmitted.
hall_id | Floor section ID; by default, it is not transmitted.
without_deleted | The status of returning without removed tables: 0—with removed tables, 1—without removed tables. The default value is 0.

### spots.getTableHallTables response parameters

Parameter | Description
--------- | -----------
response | An array of objects

Inside the `response` parameter, there is an array, each element of which contains the following parameters:

Parameter | Description
--------- | -----------
table_id | Table ID
table_num | Table number
table_title | Table name
spot_id | Location ID
table_shape | Table shape: square—square, circle—round-edged
hall_id | Floor section ID
table_x | The X-axis table coordinate
table_y | The Y-axis table coordinate
table_height | Table height
table_width | Table width
is_deleted | A status of the table removed: 0—not removed, 1—removed
status | A status of open orders on the table: 1—no open orders, 2—there are open orders

