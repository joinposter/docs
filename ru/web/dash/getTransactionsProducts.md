## dash.getTransactionsProducts: Список продуктов по всем транзакциям

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/dash.getTransactionsProducts'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&transactions_id=1,2';
 
$data = sendRequest($url);
```

> Пример ответа:

```json
{
   "response":[
      {
         "transaction_id":1,
         "product_id":169,
         "product_name":"Речная форель ",
         "modification_id":0,
         "modificator_name":null,
         "modificator_barcode":null,
         "modificator_product_code":null,
         "weight_flag":0,
         "num":2,
         "time":1527148991899,
         "workshop":2,
         "barcode":"",
         "product_code":"",
         "tax_id":0,
         "nodiscount":0,
         "payed_sum":"252.00",
         "product_sum":"252.00",
         "discount":0,
         "bonus_sum":"0.00",
         "client_id":0,
         "promotion_id":"0",
         "cert_sum":"0.00",
         "product_cost":0,
         "product_cost_netto":0,
         "product_profit":25200,
         "product_profit_netto":25200,
         "bonus_accrual":0,
         "tax_value":0,
         "tax_type":0,
         "tax_fiscal":0,
         "category_id":33
      },
      {
         "transaction_id":2,
         "product_id":168,
         "product_name":"Стейк из семги",
         "modification_id":0,
         "modificator_name":null,
         "modificator_barcode":null,
         "modificator_product_code":null,
         "weight_flag":0,
         "num":2,
         "time":1527149138470,
         "workshop":2,
         "barcode":"",
         "product_code":"",
         "tax_id":0,
         "nodiscount":1,
         "payed_sum":"0.00",
         "product_sum":"360.00",
         "discount":0,
         "bonus_sum":"0.00",
         "client_id":0,
         "promotion_id":"0",
         "cert_sum":"0.00",
         "product_cost":0,
         "product_cost_netto":0,
         "product_profit":36000,
         "product_profit_netto":36000,
         "bonus_accrual":0,
         "tax_value":0,
         "tax_type":0,
         "tax_fiscal":0,
         "category_id":33
      }
   ]
}
```

Метод возврашает список продуктов по всем транзакциям

### HTTP запрос

`GET https://joinposter.com/api/dash.getTransactionProducts`

### GET-параметры запроса dash.getTransactionsProducts

Параметр | Описание
-------- | --------
transactions_id | Обязательный параметр, список id транзакции (номеров чека) записанных через запятую

### Параметры ответа dash.getTransactionsProducts

Параметр | Описание
-------- | --------
response | Объект ответа

Внутри параметра `response` лежит массив объектов, внутри которого есть следующие параметры:

Параметр | Описание
-------- | --------
transaction_id | id чека
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
tax_value | Процент налога от суммы чека
tax_type | Тип налога: 1 — НДС, 2 — с оборота 
tax_fiscal | Налог по фискальному регистратору
category_id | Id категории в которой содержится товар
