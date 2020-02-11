## application.getInfo: Данные по приложению

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/application.getInfo'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url, 'get', []);

```

> Пример ответа:

```json
{  
   "response":{  
      "user":{  
         "id":"1",
         "name":"Demo",
         "access_mask":"2147483647",
         "email":"demo@gmail.com"
      },
      "ownerInfo":{  
         "email":"demo@gmail.com",
         "phone":"+380504813033",
         "city":"",
         "country":"UA",
         "name":"Demo",
         "company_name":"Демо-версия Poster"
      },
      "tariff":{  
         "price":0,
         "date_trial":30,
         "currency_iso_code":"USD",
         "next_pay_date":"2018-07-25 15:56:29",
         "tariff_id":2,
         "key":"showcase",
         "name":"Витрина"
      }
   }
}
```

Метод возвращает данные по приложению

### HTTP GET запрос

`GET https://joinposter.com/api/application.getInfo`

### Параметры ответа application.getInfo

Параметр | Описание
-------- | -------- 
user | Объект с информацией о пользователе который установил приложение
ownerInfo | Объект с информацией о владельце аккаунта Poster
tariff | Объект с информацией о подключенном тарифе. Передается если приложение привязанно к биллингу Poster. 

Объект `user` содержит следующие параметры: 

Параметр | Описание
-------- | -------- 
id | Id сотрудника в Poster 
name | Имя сотрудника в Poster
access_mask | Маска доступа сотрудника, содержит информацию к каким разделам Poster сотрудник имеет доступ
email | Почта сотрудника

Объект `ownerInfo` содержит следующие параметры: 

Параметр | Описание
-------- | -------- 
email | Email владельца аккаунта 
phone | Телефон владельца
city | Город владельца
country | Двухбуквенный код страны, формат ISO 3166
name | Имя владельца аккаунта
company_name | Название заведения

Объект `tatiff` содержит следующие параметры: 

Параметр | Описание
-------- | -------- 
key | Уникальный ключ тарифа
date_trial | Количество тестовых дней в тарифе
tariff_id | Уникальный идентификатор тарифного плана
next_pay_date | Дата до которой приложение оплачено в формате `Y-m-d H:i:s`
price | Стоимость тарифа в USD
name | Название тарифного плана
