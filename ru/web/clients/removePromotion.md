## clients.removePromotion: Удаление акции

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/clients.removePromotion?'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$promotion = [
  'promotion_id' => 6,
];

$data = sendRequest($url, 'post', $promotion);
```

> Пример ответа:

```json
{
  "response":true
}
```

Метод удаляет указанную акцию

!> Удаленные данные восстановлению не подлежат!

### HTTP POST запрос

`POST https://joinposter.com/api/clients.removePromotion`

### POST-параметры запроса clients.removePromotion

Параметр | Описание
-------- | --------
promotion_id | Id акции которую удаляем

### Параметры ответа clients.removePromotion

Параметр | Описание
-------- | --------
response | true, если акция успешно удалена

