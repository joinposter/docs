## storage.getWasteReasons: List of Waste Reasons

> Request example:

```php
<?
$url = 'https://joinposter.com/api/storage.getWasteReasons'
  . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);
```

> Response example:

```json
{
   "response":[
      {
         "reason_id":1,
         "name":"Истек срок годности"
      }
   ]
}
```

The method returns a list of all the waste reasons

### HTTP GET request

`GET https://joinposter.com/api/storage.getWasteReasons`

### The storage.getWasteReasons response parameters

Parameter | Description
--------- | -----------
reason_id | Waste reason ID
name | Waste reason

