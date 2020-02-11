## dash.getTransactions: Список транзакций

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/dash.getTransactions'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&dateFrom=20170905'
 . '&dateTo=20170908';

$data = sendRequest($url);
```

> Пример ответа:

```json
{
  "response":[
    {
      "transaction_id":"384960",
      "date_start":"1504641602936",
      "date_start_new":"1504641602941",
      "date_close":"1504641603008",
      "status":"2",
      "guests_count":"4",
      "discount":"0",
      "bonus":"0",
      "pay_type":"3",
      "payed_bonus":"0",
      "payed_card":"0",
      "payed_cash":"199140",
      "payed_sum":"199140",
      "payed_cert":"0",
      "tip_sum":"0",
      "sum":"180600",
      "spot_id":"1",
      "table_id":"90",
      "name":"Demo",
      "user_id":"1",
      "client_id":"0",
      "card_number":"0",
      "transaction_comment":null,
      "reason":"",
      "print_fiscal":"0",
      "total_profit":"172828",
      "table_name":"1",
      "client_firstname":null,
      "client_lastname":null,
      "date_close_date":"2017-09-05 23:00:03"
    },
    {
      "transaction_id":"384956",
      "date_start":"1504641601797",
      "date_start_new":"1504641601809",
      "date_close":"1504641601850",
      "status":"2",
      "guests_count":"5",
      "discount":"0",
      "bonus":"0",
      "pay_type":"3",
      "payed_bonus":"0",
      "payed_card":"0",
      "payed_cash":"117000",
      "payed_sum":"117000",
      "payed_cert":"0",
      "tip_sum":"0",
      "sum":"117000",
      "spot_id":"1",
      "table_id":"91",
      "name":"Максим",
      "user_id":"2",
      "client_id":"0",
      "card_number":"0",
      "transaction_comment":null,
      "reason":"",
      "print_fiscal":"0",
      "total_profit":"113487",
      "table_name":"2",
      "client_firstname":null,
      "client_lastname":null,
      "date_close_date":"2017-09-05 23:00:02"
    }
  ]
}
```

Метод возвращает список транзакций

### HTTP запрос

`GET https://joinposter.com/api/dash.getTransactions`

### GET-параметры запроса dash.getTransactions

Параметр | Описание
-------- | --------
dateFrom | Опциональный параметр, дата начала выборки в формате `Ymd`, включительно. По умолчанию дата месяц назад.
dateTo | Опциональный параметр, дата конца выборки в формате `Ymd`, включительно. По умолчанию дата текущего дня.
type | Тип статистики: `waiters` — по официанту, `spots` — заведению, `clients` — клиенту. При использовании обязательно указать `id`.
id | Id сущности по которой получать статистику, если не указано будут выданы транзакции по всем типам статистики. При использовании обязательно указать `type`.
status | Статус транзакции: 0 — все транзакции, 1 — только открытые, 2 — только закрытые, 3 — удаленные  
include_products | Признак включать товары в транзакциях в ответ, `true` — включать, `false` — нет
include_history | Признак включить историю транзакции в ответ, `true` — включать, `false` — нет
next_tr | id транзакции после которой нужно получить список транзакций
after_date_close | Транзакции после даты закрытия в формате unixtimestamp
before_date_close | Транзакции до даты закрытия в формате unixtimestamp
timezone | Опциональный параметры, если равен `client` то дата возвращается в часовом поясе аккаунта. 


### Параметры ответа dash.getTransactions

Параметр | Описание
-------- | --------
response | Объект ответа

Внутри параметра `response` лежит массив объектов, внутри каждого есть следующие параметры:

Параметр | Описание
-------- | --------
date_start | Дата открытия заказа в миллисекундах
date_close | Дата закрытия заказа в миллисекундах, 0 — если заказ еще открыт
status | Статус заказа: 1 — открыт, 2 — закрыт, 3 — удален
guests_count | Количество гостей
name | Имя официанта
discount | Скидка в процентах
bonus | Начисленный бонус в процентах от `payed_sum`
pay_type | Тип оплаты: 0 — закрыт без оплаты (причина в `reason`), 1 — оплата наличкой, 2 — оплата карточкой, 3 — смешанная оплата
payed_bonus | Сумма уплаченная бонусами в копейках
payed_card | Сумма уплаченная картой в копейках
payed_cash | Сумма уплаченная наличкой в копейках
payed_third_party | Сумма уплаченная третьей стороной в копейках
payed_sum | Сумма уплаченная "живыми деньгами", равна сумме `payed_cash` плюс `payed_card`
round_sum | Сумма округления по чеку в копейках
sum | Общая сумма заказа, без скидок в копейках
spot_id | Id заведения
table_id | Id столика
user_id | Id официанта
client_id | Id клиента
transaction_comment | Комментарий к чеку
reason | Причина закрытия счета без оплаты: 1 — гость ушел, 2 — за счет заведения, 3 — ошибка официанта
print_fiscal | Признак печати фискального чека: 0 — не печатали, 1 — печатали, 2 — фискальный возврат
total_profit | Сумма прибыли
total_profit_netto | Сумма прибыли без НДС. Возвращается если включена настройка «Считать себестоимость и прибыль нетто»
table_name | Название столика
client_firstname | Имя клиента 
client_lastname | Фамилия клиента 
products | Массив товаров в чеке
history | История действий над чеком. Содержит массив из объектов, описание параметров объекта смотрите в методе [dash.getTransactionHistory](/docs/v3/web/dash/getTransactionHistory). 

Внутри параметра `products` лежит массив объект, внутри каждого есть следующие параметры:

Параметр | Описание
-------- | --------
product_id | id товара
modification_id | id модификации
product_price | Стоимость товара
num | Количество товара в чеке
payed_sum | Уплаченная сумма
product_cost | Себестоимость товара в копейках
product_cost_netto | Себестоимость товара в копейках без НДС. Возвращается если включена настройка «Считать себестоимость и прибыль нетто»
product_profit | Прибыль по товару в копейках
product_profit_netto | Прибыль по товару в копейках без НДС. Возвращается если включена настройка «Считать себестоимость и прибыль нетто»
