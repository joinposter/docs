# Авторизация в API

Для авторизация приложений используется протокол [OAuth2](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2). 
В результате авторизации приложение получает `access_token`, с которым будет делать запросы к API.

### Шаг 1

Перейти из приложения на сайт Poster по адресу:

`https://joinposter.com/api/auth?application_id={application_id}&redirect_uri={redirect_uri}&response_type=code`

Если вы уже знаете логин аккаунта используйте:   

`https://{account}.joinposter.com/api/auth?application_id={application_id}&redirect_uri={redirect_uri}&response_type=code`


Параметр | Значение
-------- | --------
application_id | Id приложения в системе Poster, указан в настройках приложения на [dev.joinposter.com](https://dev.joinposter.com/login)
redirect_uri | URL на который пользователь направляется после первого шага авторизации. Должен точно совпадать с тем, что указан в настройках приложения на [dev.joinposter.com](https://dev.joinposter.com/login).
response_type | Строка со значением `code`


### Шаг 2

После перехода по одному из указанных выше адресов пользователь авторизуется. 
Затем подтверждает свое согласие на передачу приложению даных аккаунта. 
Доступы приложения указываются в настройках приложения на [dev.joinposter.com](https://dev.joinposter.com/login). 

После подтверждения о передачи данных пользователь будет перенаправлен обратно в приложение по адресу:
`redirect_uri?code=code&account=account`

Параметр | Значение
-------- | -------- 
code | 32 символьный код, использующийся для идентификации приложения на последнем шаге авторизации,
account | логин заведения в системе Poster, который необходимо использовать для отправки всех последующих запросов к API Poster.

### Шаг 3

Последний этап авторизации — получение `access_token`. 
Для этого приложение должно отправить POST-запрос по адресу:`https://{account}.joinposter.com/api/v2/auth/access_token`.

Где `account` — это логин заведения в системе Poster, переданный в GET-параметре во время обратного редиректа

!> Тело запроса нужно отправлять в формате form-data


#### Пример

<!-- tabs:start -->

#### ** PHP **

```php
<?php
$account = $_GET['account'];
$code = $_GET['code'];

$url = "https://$account.joinposter.com/api/v2/auth/access_token"; 

$auth = [
    'application_id'        => 76,
    'application_secret'    => '9642176a5cdfe3f65e6e00c27b668795',
    'grant_type'            => 'authorization_code',
    'redirect_uri'          => 'http://localhost:8080/',
    'code'                  => $code
];

$data = sendRequest($url, 'post', $auth);
```

#### ** cURL **

```bash
account="api-demo" # GET параметр с шага 2
code="bd8f3168d1af839cbc90d11575459465" # GET параметр с шага 2
appId=76
appSecret="9642176a5cdfe3f65e6e00c27b668795"
redirectUrl="http://localhost:8080/"

curl -X POST \
  "https://$account.joinposter.com/api/v2/auth/access_token" \
  -H 'cache-control: no-cache' \
  -H 'content-type: multipart/form-data;' \
  -F "application_id=$appId" \
  -F "application_secret=$appSecret" \
  -F 'grant_type=authorization_code' \
  -F "redirect_uri=$redirectUrl" \
  -F "code=$code"
```

<!-- tabs:end -->

<details open>
<summary>Пример ответа при успешной авторизации</summary>

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

</details>

### POST параметры запроса /api/v2/auth/access_token

Параметр | Значение
-------- | -------- 
code | 32 символьный код который вы получили на 2м шаге авторизации в GET параметре
application_id | Id приложения в системе Poster. Указан в настройках приложения на [dev.joinposter.com](/login).
application_secret | Секретный код приложения выданные при регистрации. Указан в настройках приложения на [dev.joinposter.com](/login).
redirect_uri | URL на который пользователь направляется после первого шага авторизации. Должен точно совпадать с тем, что указан в настройках приложения на [dev.joinposter.com](/login).
grant_type | Строка со значенем — `authorization_code`

### Параметры успешного ответа /api/v2/auth/access_token

Параметр | Значение
-------- | -------- 
access_token | Заветный токен который открывает доступ к API. Время жизни 2 года.
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
