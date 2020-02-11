## transactions.changeTransactionProductCount: Изменение количества товара в чеке

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/transactions.changeTransactionProductCount'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$transaction = [
    'spot_id'        => 1,
    'spot_tablet_id' => 1,
    'transaction_id' => 1950,
    'product_id'     => 112,
    'modification'   => '[{"m":19,"a":1}]',
    'count'          => 2,
];

$data = sendRequest($url, 'post', $transaction);
```

> Пример ответа:

```json
{  
  "response":{  
    "err_code":0
  }
}
```

Метод изменяет количество товара в чеке

### HTTP запрос

`POST https://joinposter.com/api/transactions.changeTransactionProductCount`

### POST-параметры запроса transactions.changeTransactionProductCount

Параметр | Описание
-------- | --------
spot_id | Id заведения
spot_tablet_id | Id терминала
transaction_id | Id чека
product_id | Id товара или тех. карты
modificator_id | Id модификатора товара, по умолчанию не передаётся
modification | Модификации тех. карты, по умолчанию не передаётся
count | Количество товара или тех. карты
time | Время операции в формате microtime, по умолчанию принимает текущее время

Внутри параметра `modification` должна быть JSON `строка`. JSON должен состоять из массива объектов, где в каждом объекте должны быть следующие параметры:

Параметр | Описание
-------- | --------
m | Id модификации тех. карты
a | Количество модификации тех. карты

### Параметры ответа transactions.changeTransactionProductCount

Параметр | Описание
-------- | --------
response | Объект ответа

Внутри параметра `response` лежит объект, внутри которого есть следующие параметры:

Параметр | Описание
-------- | --------
err_code | 0, если количество товара или тех. карты успешно изменено

В ходе выполнения могут произойти общие ошибки, их описание находится в разделе [Коды ошибок](/docs/v3/web/errors).
