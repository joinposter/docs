## dash.getTransactionProducts: Список продуктов по транзакции

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/dash.getTransactionProducts'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&transaction_id=388678';
 
$data = sendRequest($url);
```

> Пример ответа:

```json
{
  "response":[
    {
      "product_id":"908",
      "product_name":"Пицца сборная",
      "modification_id":"68",
      "modificator_name":"Сыр, Грибы, Ох. колбаски, Оливки, Средняя Ø35см",
      "modificator_barcode":"",
      "modificator_product_code":"",
      "weight_flag":"0",
      "num":"1",
      "time":"1507703516999",
      "workshop":"2",
      "barcode":"",
      "product_code":"",
      "tax_id":"4",
      "nodiscount":"1",
      "payed_sum":"45000",
      "product_sum":"45000",
      "discount":"0",
      "bonus_sum":"0",
      "round_sum":0,
      "client_id":"0",
      "promotion_id":"0",
      "cert_sum":"0",
      "product_cost":"43",
      "product_cost_netto":"36",
      "product_profit":"42707",
      "product_profit_netto":"42700",
      "bonus_accrual":"0",
      "tax_value":"5",
      "tax_type":"2",
      "tax_fiscal":"1",
      "category_id":"33"
    },
    {
      "product_id":"169",
      "product_name":"Речная форель в фольге",
      "modification_id":"0",
      "modificator_name":null,
      "modificator_barcode":null,
      "modificator_product_code":null,
      "weight_flag":"0",
      "num":"1",
      "time":"1507703509384",
      "workshop":"2",
      "barcode":"",
      "product_code":"",
      "tax_id":"4",
      "nodiscount":"1",
      "payed_sum":"55000",
      "product_sum":"55000",
      "discount":"0",
      "bonus_sum":"0",
      "round_sum":0,
      "client_id":"0",
      "promotion_id":"0",
      "cert_sum":"0",
      "product_cost":"4340",
      "product_cost_netto":"3617",
      "product_profit":"47910",
      "product_profit_netto":"47187",
      "bonus_accrual":"0",
      "tax_value":"5",
      "tax_type":"2",
      "tax_fiscal":"1",
      "category_id":"33"
    },
    {
      "product_id":"168",
      "product_name":"Стейк из сёмги",
      "modification_id":"0",
      "modificator_name":null,
      "modificator_barcode":null,
      "modificator_product_code":null,
      "weight_flag":"0",
      "num":"1",
      "time":"1507703508927",
      "workshop":"2",
      "barcode":"",
      "product_code":"",
      "tax_id":"4",
      "nodiscount":"1",
      "payed_sum":"45000",
      "product_sum":"45000",
      "discount":"0",
      "bonus_sum":"0",
      "round_sum":0,
      "client_id":"0",
      "promotion_id":"0",
      "cert_sum":"0",
      "product_cost":"2213",
      "product_cost_netto":"1844",
      "product_profit":"40537",
      "product_profit_netto":"40168",
      "bonus_accrual":"0",
      "tax_value":"5",
      "tax_type":"2",
      "tax_fiscal":"1",
      "category_id":"33"
    }
  ]
}
```

Метод возврашает список продуктов по транзакции

### HTTP запрос

`GET https://joinposter.com/api/dash.getTransactionProducts`

### GET-параметры запроса dash.getTransactionProducts

Параметр | Описание
-------- | --------
transaction_id | Обязательный параметр, id транзакции (номер чека)

### Параметры ответа dash.getTransactionProducts

Параметр | Описание
-------- | --------
response | Объект ответа

Внутри параметра `response` лежит объект, внутри которого есть следующие параметры:

Параметр | Описание
-------- | --------
product_id | id товара
product_name | Название товара
modification_id | id модификатора. Если без модификатора то 0.
modificator_name | Название модификатора
modificator_barcode | Штрих-код  модификатора
modificator_product_code | SKU модификатора
num | Количество товара в чеке
time | Время последнего обновления количества товара в чеке, измеряется в миллисекундах 
workshop | id цеха
barcode | Штрих-код товара
product_code | SKU товара
tax_id | id налога
fiscal | Признак фискального чека: 1 — фискальный, 0 — нефискальный
nodiscount | Признак распространяются ли скидки и бонусы на товар: 0 — да, 1 — нет
payed_sum | Уплаченная сумма в копейках
product_sum | Стоимость товара в копейках
discount | Процент скидки примененный к чеку
bonus_sum | Сумма бонуса в рублях\гривнах
client_id | id клиента
promotion_id | id акции
cert_sum | Сумма уплаченная сертификатом
product_cost | Себестоимость товара
product_cost_netto | Себестоимость товара без НДС. Возвращается если включена настройка «Считать себестоимость и прибыль нетто»
product_profit | Прибыль 
product_profit_netto | Прибыль без НДС. Возвращается если включена настройка «Считать себестоимость и прибыль нетто»
bonus_accrual | Начислено бонусов
round_sum | Сумма округления по товару
tax_value | Процент налога от суммы чека
tax_type | Тип налога: 1 — НДС, 2 — с оборота 
tax_fiscal | Налог по фискальному регистратору
category_id | Id категории в которой содержится товар
