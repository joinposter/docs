# Авторизация в админ. панели


Manage платформа позволяет встраивать в админ-панель Poster iFrame с вашим сайтом. 
Чтобы включить Manage платформу в аккаунте разработчика включите переключатель **Manage platform** и укажите адрес страницы веб-приложения, который будет открываться в окне iframe.

<img src="/img/site/docs/manage-platform.jpg" alt="Manage Platform setup">


Просле загрузки iFrame, генерируется код авторизации и конкатенируется к адресу страницы 
который вы указали в аккаунте разработчика, например:

`http://example.com/?code={code}`

Чтобы получить информации об аккаунте необходимо отправить HTTP POST запрос:

`POST https://joinposter.com/api/v2/auth/manage`

!> Тело запроса нужно отправлять в формате form-data

!> Чтобы убрать прилодер загрузки, добавьте скрипт к себе на страницу:

```javascript
window.addEventListener('load', function () {
        top.postMessage({ hideSpinner: true }, '*')
}, false);
```


> Пример авторизации:
 
```php
<?php

$auth = [
    'application_id'     	=> 41, 
    'application_secret' 	=> '123123', 
    'code'          		=> '74367937cf906c097931a3888adf7a84',
];
$auth['verify'] = md5(implode(':', $auth));

$data = sendRequest('https://joinposter.com/api/v2/auth/manage', 'post', $auth);

```

> Ответ при успешной обработке запроса: 

```json
{
   "access_token":"861052:02391570ff9af128e93c5a771055ba88",
   "account_number":"861052",
   "user":{
      "id":4,
      "name":"Poster",
      "email":"dev@joinposter.com",
      "role_id":3
   },
   "ownerInfo":{
      "email":"dev@joinposter.com",
      "phone":"+380684152664",
      "city":"",
      "country":"RU",
      "name":"Poster",
      "company_name":"dev-example"
   },
   "tariff":{
      "key":"pricing-plan-1",
      "next_pay_date":"2018-05-31 11:52:41",
      "price":2
   }
}
```

> Примеры ошибок 

```json
{
  "error":34,
  "message":"Поле application_id обязательное для заполнения", 
  "field": "application_id"
}
```

```json
{
  "error":143,
  "message":"Requested code's application doesn't exist", 
  "field":"application_id"
}
```

```json
{
  "error":142,
  "message":"Verify code is not correct", 
  "field": "verify"
}
```



### POST параметры запроса

Параметр | Описание
-------- | --------
application_id | Id приложения в системе Poster. Указан в настройках приложения на [dev.joinposter.com](/login).
application_secret | Секретный код приложения выданные при регистрации. Указан в настройках приложения на [dev.joinposter.com](/login).
code | 32-символьный код который вы получили на предидущем этапе авторизации 
verify | md5 из конкатенированный application_id, application_secret и code, разделенных двоеточием

### Параметры успешного ответа:

Параметр | Значение
-------- | -------- 
access_token | Заветный токен который открывает доступ к API
account_number | Уникальный идентификатор аккаунта в Poster
user | Объект с информацией о пользователе который установил приложение
ownerInfo | Объект с информацией о владельце аккаунта Poster
tariff | Объект с информацией о подключенном тарифе. Передается если приложение привязанно к биллингу Poster.

Объект `user` содержит следующие параметры: 

Параметр | Значение
-------- | -------- 
id | Id сотрудника в Poster который подключил приложение
name | Имя сотрудника в Poster
email | Почта сотрудника
role_id | Должность сотрудника который подключил приложение. Если подключил владелец аккаунта `role_id=3`.

Объект `ownerInfo` содержит следующие параметры: 

Параметр | Значение
-------- | -------- 
email | Email владельца аккаунта 
phone | Телефон владельца
city | Город владельца
country | Двухбуквенный код страны, формат ISO 3166
name | Имя владельца аккаунта
company_name | Название заведения

Объект `tariff` содержит следующие параметры: 

Параметр | Описание
-------- | -------- 
key | Уникальный ключ тарифа
date_trial | Количество тестовых дней в тарифе
tariff_id | Уникальный идентификатор тарифного плана
next_pay_date | Дата до которой приложение оплачено `Y-m-d H:i:s`
price | Стоимость тарифа в USD
name | Название тарифного плана


### Параметры ошибки ответа /api/v2/auth/access_token

Параметр | Значение
-------- | -------- 
code | Код ошибки, значения кодов ошибок смотрите в [таблице](/docs/v3/web/errors) 
error_type | Тип сообщения об ошибке
error_message | Сообщение ошибки
