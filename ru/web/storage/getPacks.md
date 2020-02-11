## storage.getPacks: Список фасовок

>  Пример запроса:

```php
<?
$url = 'https://joinposter.com/api/storage.getPacks' 
  . '?format=json'
  . '&token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);
```

> Пример ответа:

```json
{
  "response":[
    {
      "pack_id":"1",
      "name":"",
      "unit":"p",
      "count":"0.0000",
      "type":"0"
    },
    {
      "pack_id":"2",
      "name":"",
      "unit":"l",
      "count":"0.0000",
      "type":"0"
    },
    {
      "pack_id":"3",
      "name":"",
      "unit":"kg",
      "count":"0.0000",
      "type":"0"
    },
    {
      "pack_id":"5",
      "name":"Пак молока",
      "unit":"p",
      "count":"20.0000",
      "type":"1"
    },
    {
      "pack_id":"6",
      "name":"Вода очищенная",
      "unit":"l",
      "count":"20.0000",
      "type":"1"
    }
  ]
}
```

Запрос на получение списка всех фасовок.

### HTTP запрос

`GET https://joinposter.com/api/storage.getPacks`


### Параметры ответа storage.getPacks

Параметр | Описание
-------- | --------
pack_id | id фасовки
name | Название фасовки
unit | Единица измерения: kg — кг, p — шт, l — л
count | Количество в шт, кг или литрах
type | Тип фасовки: 0 — базовый, 1 — пользовательский
