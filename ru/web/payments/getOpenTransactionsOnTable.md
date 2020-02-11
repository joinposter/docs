## payments.getOpenTransactionsOnTable: список открытых чеков на столике

>  Пример запроса:

```php
<?
$url = 'https://joinposter.com/api/payments.getOpenTransactionsOnTable?' .
  'format=json';

$application_secret = '123123123123';

$request = [
  'type' => 'application-name',
  'merchant_id' => 3432343,
  'table_id' => 41,
];

$request['sign'] = md5(implode(':', $request) . ':' . $application_secret);

$url .= '&' . http_build_query($request);

$answer = sendRequest($url);
```

> Пример ответа:

```json
{
  "response":[
    {
      "order_id":30139,
      "transaction_id":1484233370643,
      "date_open":1484233375235,
      "payed_sum":127.02,
      "products":[
        {
          "product_name":"Венский суп Гуляш"
        },
        {
          "product_name":"Медальоны из телятины с овощами гриль"
        },
        {
          "product_name":"Хлеб белый собственной выпечки"
        },
        {
          "product_name":"Кальян",
          "modificator_name":"на соке"
        },
        {
          "product_name":"Соус BBQ к блюду"
        },
        {
          "product_name":"Pepsi 300 ml"
        }
      ]
    },
    {
      "order_id":30946,
      "transaction_id":1485341938799,
      "date_open":1485341938872,
      "payed_sum":190,
      "products":[
        {
          "product_name":"Кролик по-охотничьи"
        }
      ]
    }
  ]
}
```

Возвращает стороннему платежному сервису заказы, что открыты в данный момент на конкретном столике.

### HTTP запрос

`GET https://joinposter.com/api/payments.getOpenTransactionsOnTable`

### GET-параметры запроса payments.getOpenTransactionsOnTable

Параметр | Описание
--------- | -----------
type | Ключевое имя платежной системы, которое отправляет запрос. Под систему заводится отдельное приложение в системе Poster, где и указывается данное имя.
merchant_id | Идентификатор клиента Poster во внутренней базе платежной системы
table_id | Идентификатор столика, для которого нужно получить открытые заказы
sign | Подпись запроса, является md5 хешем от строки, где через двоеточие соединены значения следующих переменных: type, merchant_id, table_id, application_secret.

application_secret — секретная строка приложения. Как и переменная type, выдается платежной системе во время создания под неё приложения в Poster.

### Параметры ответа payments.getOpenTransactionsOnTable

Параметр | Описание
--------- | -----------
order_id | Идентификатор заказа, который отображается в статистике и печатается на чеках
transaction_id | Идентификатор заказа, используемый для последующего проведения платежа
date_open | Время создания заказа в формате timestamp с миллисекундами
payed_sum | Сумма, которую должен оплатить посетитель за заказ (в гривнах/рублях)
products | Список заказанных посетителем товаров. Каждый элемент массива содержит имя товара в виде поля product_name, а также может содержать поле modificator_name, если это модификация товара.
