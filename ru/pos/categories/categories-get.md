## categories.get: Получить категорию товаров

> Пример запроса:

```javascript
var result = await Poster.categories.get(1);

console.log(result); // { success: true, category: {...} }
```

Метод получает данные категории по ID, тип данных [Category](/docs/v3/pos/types/category).

### Аргументы

Аргумент | Описание
-------- | --------
1-й, id | ID категории

### Ответ

Функция возвращает Promise, который вернет объект с категорией 

Параметр | Описание
-------- | --------
success | Результат, удалось ли найти категорию: `true` — удалось, `false` — произошла ошибка
category | Объект типа [Category](/docs/v3/pos/types/category). Возвращется если `success` равен `true` 
