## dash.getTransaction: Получение чеков

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/dash.getTransaction'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&transaction_id=330660'
 . '&include_history=true'
 . '&include_products=true';

$data = sendRequest($url);
```

> Пример ответа:

```json
{
   "response":[
      {
         "transaction_id":"330660",
         "date_start":"1518873040083",
         "date_start_new":"1518873041556",
         "date_close":"1518873046314",
         "status":"2",
         "guests_count":"2",
         "discount":"0",
         "bonus":"0",
         "pay_type":"3",
         "payed_bonus":"0",
         "payed_card":"0",
         "payed_cash":"2750",
         "payed_sum":"2750",
         "payed_cert":"0",
         "payed_third_party":"0",
         "round_sum":"0",
         "tip_sum":"0",
         "tips_card": "0",
         "tips_cash": "0",
         "sum":"2750",
         "spot_id":"1",
         "table_id":"94",
         "name":"Анна",
         "user_id":"1",
         "client_id":"0",
         "card_number":"0",
         "transaction_comment":null,
         "reason":"",
         "print_fiscal":"0",
         "total_profit":"-8786",
         "total_profit_netto":"-6789",
         "table_name":"5",
         "client_firstname":null,
         "client_lastname":null,
         "date_close_date":"2018-02-17 16:10:46",
         "products":[
            {
               "product_id":"162",
               "modification_id":"0",
               "num":"1",
               "product_price":"1050",
               "payed_sum":"1050",
               "product_cost":"4536",
               "product_cost_netto":"3780",
               "product_profit":"-3486",
               "product_profit_netto":"-2905"
            },
            {
               "product_id":"161",
               "modification_id":"0",
               "num":"1",
               "product_price":"1700",
               "payed_sum":"1700",
               "product_cost":"7000",
               "product_cost_netto":"5833",
               "product_profit":"-5300",
               "product_profit_netto":"-3884"
            }
         ],
         "history":[
            {
               "history_id":"2485357",
               "type_history":"open",
               "spot_tablet_id":"1",
               "time":"1518873040083",
               "user_id":"1",
               "value":"1",
               "value2":"94",
               "value3":"2",
               "value4":"0",
               "value5":"0",
               "value_text":null
            },
            {
               "history_id":"2485358",
               "type_history":"additem",
               "spot_tablet_id":"1",
               "time":"1518873041556",
               "user_id":"1",
               "value":"162",
               "value2":"0",
               "value3":"0",
               "value4":"0",
               "value5":"0",
               "value_text":{
                  "price":10.5
               }
            },
            {
               "history_id":"2485359",
               "type_history":"additem",
               "spot_tablet_id":"1",
               "time":"1518873042008",
               "user_id":"1",
               "value":"161",
               "value2":"0",
               "value3":"0",
               "value4":"0",
               "value5":"0",
               "value_text":{
                  "price":17
               }
            },
            {
               "history_id":"2485360",
               "type_history":"close",
               "spot_tablet_id":"1",
               "time":"1518873046314",
               "user_id":"1",
               "value":"3",
               "value2":"2750",
               "value3":"0",
               "value4":"0",
               "value5":"0",
               "value_text":{
                  "payments":{
                     "cash":27.5
                  }
               }
            }
         ]
      }
   ]
}
```

Метод возвращает список с одним чеком

### HTTP запрос

`GET https://joinposter.com/api/dash.getTransaction`

### GET-параметры запроса dash.getTransaction

Параметр | Описание
-------- | --------
transaction_id | Обязательный параметр, номер чека по которому возвращать информацию 
include_products | Признак включать товары в транзакциях в ответ, `true` — включать, `false` — нет
include_history | Признак включить историю транзакции в ответ, `true` — включать, `false` — нет
timezone | Опциональный параметры, если равен `client` то дата возвращается в часовом поясе аккаунта. 
type | Тип статистики: `waiters` — по официанту, `spots` — заведению, `clients` — клиенту. При использовании обязательно указать `id`.
id | Id сущности по которой получать статистику, если не указано будут выданы транзакции по всем типам статистики. При использовании обязательно указать `type`.
status | Статус транзакции: 0 — все транзакции, 1 — только открытые, 2 — только закрытые, 3 — удаленные  


### Параметры ответа dash.getTransaction

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
tip_sum | Сумма процента за обслуживание в копейках
tips_card | Сумма чаевых уплаченная картой в копейках
tips_cash | Сумма чаевых уплаченная наличными в копейках
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
