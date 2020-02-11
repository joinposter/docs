## categories.getAll: Получить все категории товаров

> Пример запроса:

```javascript
var result = await Poster.categories.getAll();

console.log(result); // { success: true, categories: [...] }
```

Метод получает данные категории по ID, тип данных [Category](/docs/v3/pos/types/category).


### Ответ

Функция возвращает Promise, который возвращает объект со списком категорий

Параметр | Описание
-------- | --------
success | Результат, удалось ли вернуть все категории: `true` — удалось, `false` — произошла ошибка
categories | Массив из объектов типа [Category](/docs/v3/pos/types/category). Возвращется если `success` равен `true` 
