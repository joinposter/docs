## Authorization in the management console

Manage platform allows you to embed your webpage into Poster management console. 
To enable Manage Platform turnon switch in application settings in developer account and 
specify the address of the web application page that will be opened in the iFrame.

<img src="/img/site/docs/manage-platform.jpg" alt="Manage Platform setup">


After the iframe loads, an authorization code is generated and added to the page address, for example:

`http://example.com/?code={code}`


To receive account information, you must send an HTTP request:

`POST https://joinposter.com/api/v2/auth/manage`

!> To remove a preloader, add the script to your page.

```javascript
window.addEventListener('load', function () {
        top.postMessage({hideSpinner: true}, '*')
}, false);
```




> Authorization example:
 
```php
<?php
$url = "https://joinposter.com/api/v2/auth/manage";

$auth = [
    'application_id'     	=> 41, 
    'application_secret' 	=> '123123', 
    'code'          		=> '74367937cf906c097931a3888adf7a84',
];
$auth['verify'] = md5(implode(':', $auth));

$data = sendRequest($url, 'post', $auth);

```

> Response to a successful request processing:  

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

> Errors examples:

```json
{
  "error":34,
  "message":"Fieild client_id is required", 
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

### POST parameters of the request: /api/v2/auth/manage

Parameter | Description
--------- | -----------
application_id | Application Id in the Poster system. You can find it in [developer account](/en/login) → application settings.
application_secret | Application secret code issued at registration. You can find it in [developer account](/en/login) → application settings.
code | 32-character code you received at previous step of the authorization
verify | md5 from the concatenated client_id, client_secret, and code, with a colon delimiter

### Successful response parameters:

Parameter | Value
--------- | -----
access_token | The one and only token that opens access to API
account_number | Unique account identifier in Poster system
user | An object with info about the user who installed app
ownerInfo | Object with information about account owner of the Poster account
tariff | The object with information about the connected tariff. Dispatched if the application is tied to Poster billing.


An `user` object contains the following parameters:

Parameter | Description
--------- | -----------
id | The employee ID in Poster. This employee has authorized application installation.
name | The employee name in Poster
email | The employee’s email address
role_id | The employee’s position in a venue. Account owner has `role_id=3`.

An `ownerInfo` object contains the following parameters

Parameter | Value
--------- | -----
email | The owners’s email address
phone | The owners’s phone
city | City
country | Two letter country code in the ISO 3166 format. 
name | The owners’s name
company_name | Location name

A `tariff` object contains the following parameters

Parameter | Value
--------- | -----
key | Unique tariff key
date_trial | Total amount of trial days 
next_pay_date | Date to which the application is paid in `Y-m-d H:i:s` format
price | Tariff price in USD
name | Tariff name


### Failed response parameters:

Параметр | Значение
-------- | -------- 
code | Error code, description of all error codes are listed in the [table](/en/docs/v3/web/errors) 
error_type | Type of error
error_message | Human readable error message
