## payments.addTransactionPayment: уведомление об оплате клиентского заказа

>  Пример запроса:

```php
<?
$url = 'https://joinposter.com/api/payments.addTransactionPayment?' .
  'format=json';

$application_secret = '123123123123';

$payment = [
  'type' => 'application-name',
  'merchant_id' => 3432343,
  'transaction_id' => '1474012061849',
  'payed_sum' => 369.00,
  'credited_sum' => 365.31,
];

$payment['sign'] = md5(implode(':', $payment) . ':' . $application_secret);

$answer = sendRequest($url, 'post', $payment);
```

> Пример ответа:

```json
{
  "response":{
    "status":"accept"
  }
}
```

Уведомление системы Poster об успешной оплате клиентского заказа через сторонний платежный сервис.

### HTTP запрос

`POST https://joinposter.com/api/payments.addTransactionPayment`

### POST-параметры запроса payments.addTransactionPayment

Параметр | Описание
--------- | -----------
type | Ключевое имя платежной системы, которое отправляет запрос о поступившей оплате. Под систему заводится отдельное приложение в системе Poster, где и указывается данное имя.
merchant_id | Идентификатор клиента Poster во внутренней базе платежной системы
transaction_id | id заказа, который был оплачен через платежную систему
payed_sum | Сумма заказа, которую оплатил посетитель (в гривнах/рублях)
credited_sum | Сумма, которая была зачислена на р/с клиента Poster (в гривнах/рублях). Это сумма заказа минус комиссия эквайринга.
sign | Подпись запроса, является md5 хешем от строки, где через двоеточие соединены значения следующих переменных: type, merchant_id, transaction_id, payed_sum, credited_sum, application_secret.

application_secret — секретная строка приложения. Как и переменная type, выдается платежной системе во время создания под неё приложения в Poster.

### Параметры ответа payments.addTransactionPayment

Параметр | Описание
--------- | -----------
status | В случае успешной обработки запроса, будет содержать значение accept
