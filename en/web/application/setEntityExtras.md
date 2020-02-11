## application.setEntityExtras: Update Additional Entity Data

> Request example:

```php
// Saves side system product id 
<?php
$url = 'https://joinposter.com/api/application.setEntityExtras'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$extras = [
    "entity_type"   => "product",
    "entity_id"     => 4,
    "extras"        => [
        "sideId" => "1"
    ]
];

$data = sendRequest($url, 'post', $extras);

```

> Response example:

```json
{
  "response":true
}
```

> Request example:

```php
// Save auth token in global settings 
<?php
$url = 'https://joinposter.com/api/application.setEntityExtras'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$extras = [
    "entity_type"   => "settings",
    "extras"        => [
        "token" => "lva23gds1793skd0123apsod10230wqoe0oe01"
    ]
];

$data = sendRequest($url, 'post', $extras);

```

> Response example:

```json
{
  "response":true
}
```

Poster has a concept of an entity, for example, a register, the location tables, a customer, a waiter, etc. 
You can use this method to expand information about any entity. 
For example, you write an application on the POS platform; you have to authorize a user and save his token for further requests. 
When you restart your tablet, the token will be deleted from memory, but you can save it in the settings entity. 
Now when the register boots, you can get all the settings by the `settings.getAllSettings` method or in the `Poster.settings.extras` object.

### HTTP request

`POST https://joinposter.com/api/application.setEntityExtras`

### POST parameters of the application.setEntityExtras request

Parameter | Description
--------- | -----------
entity_type | A mandatory parameter, the type of an entity the parameters are written into. The entity variants available are described below.
entity_id | A mandatory parameter, the ID of an entity the `extras` object will be written into. For example, for the `access.getTablets` method—`tablet_id`.
extras | A mandatory parameter, the object the properties of which will be written into the entity

### The application.setEntityExtras response parameters

Parameter | Description
--------- | -----------
response | The request result; `true` if the request was successful

### List of entities extras can be added to

Entity | Description
--- | ---
spot | Location
tablet | Register
staff | Employee
clients_group | Customer group
product | Product or dish
ingredient | Ingredient
menu_category | Product or modifier category
ingredients_category | Ingredient category
client | Location customer
settings | Account settings, a global entity. `entity_id` does not have to be transmitted in the request.
