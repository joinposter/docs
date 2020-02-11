## finance.updateCategory: Изменение финансовой категории

> Пример запроса:

```php
<?php
$url = 'https://joinposter.com/api/finance.updateCategory'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$category = [
    'category_id'       => 13,
    'category_name'     => 'Коммуналка',
    'category_parent'   => 0,
    'operations_in'     => 1, 
    'operations_out'    => 1,

];

$data = sendRequest($url, 'post', $category);
```

> Пример ответа:

```json
{
  "response":13
}
```

Метод изменяет финансовую категорию 

### HTTP запрос

`POST https://joinposter.com/api/finance.updateCategory`

### POST-параметры запроса finance.updateCategory

Параметр | Описание
-------- | --------
category_id | Id изменяемой категории
category_name | Название категории
category_parent | id родительской категории, если 0 то текущая категория отобразиться на самом верхнем уровне
operations_in | Допустимы ли транзакции типа доходы: 1 — допустимы, 0 — нет  
operations_out | Допустимы ли транзакции типа расходы: 1 — допустимы, 0 — нет 

### Параметры ответа finance.updateCategory

Параметр | Описание
-------- | --------
response | id измененной категории
