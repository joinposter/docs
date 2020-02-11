## storage.getSuppliers: Получить всех поставщиков

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/storage.getSuppliers'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);
```

> Пример ответа:

```json
{
  "response":[
    {
      "supplier_id":"1",
      "supplier_name":"Закупщик",
      "supplier_phone":"+7 499 555 55 55",
      "supplier_adress":"",
      "supplier_comment":"",
      "supplier_code":"",
      "supplier_tin":"",
      "delete":"0"
    },
    {
      "supplier_id":"2",
      "supplier_name":"Напитков Иван",
      "supplier_phone":"0956734678",
      "supplier_adress":"ул. Лесная 3",
      "supplier_comment":"",
      "supplier_code":"",
      "supplier_tin":"",
      "delete":"0"
    },
    {
      "supplier_id":"3",
      "supplier_name":"Овощной Иван",
      "supplier_phone":"0987658943",
      "supplier_adress":"ул. Байкальская",
      "supplier_comment":"",
      "supplier_code":"",
      "supplier_tin":"",
      "delete":"0"
    }
  ]
}
```

Метод возвращает всех поставщиков

### HTTP запрос

`GET https://joinposter.com/api/storage.getSuppliers`

### GET-параметры запроса storage.getSuppliers

Параметр | Описание
-------- | --------
id_1c | Опциональный параметр, `true` если возвращать id_1   

### Параметры ответа storage.getSuppliers

Параметр | Описание
-------- | --------
response | Объект ответа

Внутри параметра `response` лежит массив, в каждом элементе которого есть следующие параметры:

Параметр | Описание
-------- | --------
supplier_id | id поставщика
supplier_name | Имя поставщика
supplier_phone | Номер поставщика
supplier_adress | Адрес поставщика
supplier_comment | Комментарий 
supplier_code | Уникальный идентификационный номер юридического лица
supplier_tin | ИНН поставщика
delete | Признак удален ли поставщик: 1 — удален, 0 — нет
