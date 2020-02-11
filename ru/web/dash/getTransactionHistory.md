## dash.getTransactionHistory: История транзакции

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/dash.getTransactionHistory'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&transaction_id=388678';

$data = sendRequest($url);
```

> Пример ответа:

```json
{
  "response":[
    {
      "transaction_id":"388678",
      "type_history":"print",
      "time":"1507703522429",
      "value":"1",
      "value2":"2147483647",
      "value3":"0",
      "value_text":null,
      "spot_tablet_id":"1"
    },
    {
      "transaction_id":"388678",
      "type_history":"close",
      "time":"1507703520358",
      "value":"3",
      "value2":"145000",
      "value3":"0",
      "value_text":"{\"payments\":{\"cash\":1450}}",
      "spot_tablet_id":"1"
    },
    {
      "transaction_id":"388678",
      "type_history":"additem",
      "time":"1507703508927",
      "value":"168",
      "value2":"0",
      "value3":"0",
      "value_text":"{\"price\":450}",
      "spot_tablet_id":"1"
    },
    {
      "transaction_id":"388678",
      "type_history":"open",
      "time":"1507703507594",
      "value":"1",
      "value2":"95",
      "value3":"3",
      "value_text":null,
      "spot_tablet_id":"1"
    }
  ]
}
```

Метод возвращает историю действий по транзакции

### HTTP запрос

`GET https://joinposter.com/api/dash.getTransactionHistory`

### GET-параметры запроса dash.getTransactionHistory

Параметр | Описание
-------- | --------
transaction_id | Обязательный параметр, id транзакции (номер чека)


### Параметры ответа dash.getTransactionHistory

Параметр | Описание
-------- | --------
response | Объект ответа

Внутри параметра `response` лежит массив объектов, внутри каждого есть следующие параметры:

Параметр | Описание
-------- | --------
transaction_id | Номер чека
type_history | Действие совершенное над чеком, возможные значения описаны ниже
time | Время действия в миллисекундах
spot_tablet_id | Id терминала
value_text | Текстовое значение, соответствующее конкретному действию. Может содержать в том числе и json.
value, value2, value3 | В зависимости от type_history означает следующее:  

Значения параметров `value`, `value2`, `value3` в зависимости `type_history`:

### open — Открыт счет

 * value — id официанта 
 * value2 — id столика
 * value3 — 0

### comment  — Добавлен комментарий

 * value — 0 
 * value2 — 0 
 * value3 — 0
 * value_text — значение комментария  

### close — Напечатан чек и закрыт счет

 * value — 0 
 * value2 — Общая сумма 
 * value3 — 0
 * value_text — JSON строка. В поле `paymets` содержится объект с полями: `cash` — сумма оплачена наличными, `card` — картой, `cert` — сертификатом.   

### delete — Чек удален

 * value — id товара 
 * value2 — 0
 * value3 — id модификатора. Если не без модификатора — 0

### print — Напечатан чек

 * value — id официанта 
 * value2 — время
 * value3 — 0 

### sendtokitchen — Отправлен бегунок на кухню

 * value — id товара
 * value2 — id модификатора. Если не без модификатора — 0 
 * value3 — Количество товара 

### additem — Добавлен товар

 * value — id добавленно товара
 * value2 — 0 
 * value3 — id модификатора. Если не без модификатора — 0
 * value_text — JSON строка c полем `price` — цена товара с которой его добавили к заказу

### settable — Перенос заказа на другой стол

 * value — id столика 
 * value2 — 0
 * value3 — 0 

### changeitemcount —  Изменено количество товара, если `value2` — 0 то товар удален

 * value — id товара 
 * value2 — количество товара
 * value3 — id модификатора. Если не без модификатора — 0  

### deleteitem — Удален товар
 
 * value — id удаленного товара
 * value2 — 0 
 * value3 — id модификатора. Если не товар без модификатора — 0

### setclient  — Добавлен клиент
 * value — id клиента
 * value2 — Размер скидки
 * value3 — 0

