## Authorization in API

To authorize applications, an [OAuth2](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2) protocol is used. 
As a result of authorization, the application gets an `access_token` to make API requests with.

### Step 1

Go from the app to the Poster website at URL:

`https://joinposter.com/api/auth?client_id={client_id}&redirect_uri={redirect_uri}&response_type=code`

If you know the account login, use:

`https://{account}.joinposter.com/api/auth?application_id={application_id}&redirect_uri={redirect_uri}&response_type=code`


Parameter | Value
--------- | -----
application_id | Application Id in the Poster system. You can find it your [developer account](/login).
redirect_uri | The application address to go back to from the Poster system after the first authorization step. This address must match exactly the one specified in the application settings in the Poster system.
response_type | A line with a `code` value

### Step 2

After switching to one of the above addresses, the user logs in. 
He then confirms that he agrees to the transmission of certain data to the application.

After confirming the application access to account data, the user will be redirected back to the application at: 
`redirect_uri?code=code&account=account`

Parameter | Value
--------- | -----
code | 32-character code used to authenticate the application at the last authorization step
account | Location login in the Poster system to use to send all the subsequent requests to the Poster API.

### Step 3


The last authorization step is getting an `access_token`. 
To get it, the application must send a POST request to the following address:`https://{account}.joinposter.com/api/v2/auth/access_token`

In which an `account` is the location login in the Poster system, received from GET-parameter during the redirect.

!> Request body should be sent in form-data format

#### Request example: 

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
account="api-demo" # GET-parameter from step 2
code="bd8f3168d1af839cbc90d11575459465" # GET-parameter from step 2
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
<summary>Example of a response on successful authorization</summary>

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


### POST parameters of the /api/v2/auth/access_token request


Parameter | Value
--------- | -----
application_id | Application Id in the Poster system. You can find it in [developer account](/en/login) → application settings.
application_secret | Application secret code issued at registration. You can find it in [developer account](/en/login) → application settings.
code | 32-character code you received at Step 2 of the authorization
grant_type | A line with an `authorization_code` value
redirect_uri | The address the user will be redirected to after the authorization. This address must match exactly the one specified in the application settings in the Poster system.


### Successful response parameters:

Parameter | Value
--------- | -----
access_token | The one and only token that opens access to API. Valid for 2 years.
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
