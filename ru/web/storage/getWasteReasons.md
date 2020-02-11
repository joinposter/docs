## storage.getWasteReasons: Список причин списания

>  Пример запроса:

```php
<?
$url = 'https://joinposter.com/api/storage.getWasteReasons'
  . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);
```

> Пример ответа:

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

Метод возвращает список всех причин списания

### HTTP GET запрос

`GET https://joinposter.com/api/storage.getWasteReasons`

### Параметры ответа storage.getWasteReasons

Параметр | Описание
-------- | ---------
reason_id | id причины списания
name | Причина списания
