## finance.createCategory: Создание новой финансовой категории

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/finance.createCategory'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$category = [
    'category_name'     => 'Коммуналка',
    'category_parent'   => 0,
    'operations_in'     => 0, 
    'operations_out'    => 1

];

$data = sendRequest($url, 'post', $category);
```

> Пример ответа:

```json
{
  "response":6
}
```

Метод созадет новую финансовую категорию

### HTTP запрос

`POST https://joinposter.com/api/finance.createCategory`

### POST-параметры запроса finance.createCategory

Параметр | Описание
-------- | --------
category_name | Название категории
category_parent | id родительской категории, если 0 то текущая категория отобразиться на самом верхнем уровне
operations_in | Допустимы ли транзакции типа доходы: 1 — допустимы, 0 — нет  
operations_out | Допустимы ли транзакции типа расходы: 1 — допустимы, 0 — нет

### Параметры ответа finance.createCategory

Параметр | Описание
-------- | --------
response | id созданной категории
