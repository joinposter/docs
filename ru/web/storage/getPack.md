## storage.getPack: Получить фасовку

>  Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/storage.getPack' 
  . '?format=json'
  . '&token=687409:4164553abf6a031302898da7800b59fb'
  . '&pack_id=4';

$data = sendRequest($url);
```
> Пример ответа:

```json
{
  "response":{
    "pack_id":"5",
    "name":"Пак молока",
    "unit":"p",
    "count":"20.0000",
    "type":"1"
  }
}
```

Метод возвращает данные конкретной фасовки.

### HTTP запрос

`GET https://joinposter.com/api/storage.getPack`

### GET-параметры запроса storage.getPack

Параметр | Описание
-------- | --------
pack_id | Id фасовки, для которой необходимо вернуть детальные данные

### Параметры ответа storage.getPack

Параметр | Описание
-------- | --------
pack_id | id фасовки
name | Название фасовки
unit | Единица измерения: kg — кг, p — шт, l — л
count | Количество в шт, кг или литрах
type | Тип фасовки: 0 — базовый, 1 — пользовательский
