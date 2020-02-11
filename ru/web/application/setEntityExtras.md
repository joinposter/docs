## application.setEntityExtras: Изменение дополнительных данных сущности 

> Пример запроса:

```php
// Сохраняем id товара в сторонней системе
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

> Пример ответа:

```json
{
  "response":true
}
```

> Пример запроса:

```php
// Сохраняем токен авторизации в глобальных настройках 
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

> Пример ответа:

```json
{
  "response":true
}
```




В Poster есть понятие сущности, например: терминал, столы в заведении, клиент, официант и т.п. 
Этим методом вы можете расширить информацию о любой сущности. 
Например, вы пишите приложение на POS платформе, вам нужно авторизовать пользователя и сохранить его токен для дальнейших запросов. 
При перезагруке планшета, токен удалится из памяти, но вы можете сохранить его в сущности settings. 
Теперь когда терминал загрузится, все настройки можно получить методом `settings.getAllSettings` или в объекте `Poster.settings.extras`.      


### HTTP запрос

`POST https://joinposter.com/api/application.setEntityExtras`

### POST-параметры запроса application.setEntityExtras

Параметр | Описание
-------- | --------
entity_type | Обязательный параметр, тип сущности в которую записываются параметры. Доступные варианты сущностей описаны ниже.
entity_id | Обязательный параметр, id сущности в которую будет записан объект `extras`. Например, для метода `access.getTablets` — `tablet_id`. 
extras | Обязательный параметр, объект поля которого будут записаны в сущность

### Параметры ответа application.setEntityExtras

Параметр | Описание
-------- | --------
response | Результат запроса, `true` — если запрос выполнен успешно

### Список сущностей которым можно добавлять extras

Сущность | Описание
-------- | --------
spot | Заведение 
tablet | Терминал
staff | Сотрудник
clients_group | Группа клиента
product | Товар или тех. картра
ingredient | Ингредиент
menu_category | Категория товара или модификатора
ingredients_category | Категория ингредиента
client | Клиент заведения
settings | Настройки аккаунта, глобальная сущность. В запросе `entity_id` передавать не обязательно.
transactions | Чеки
