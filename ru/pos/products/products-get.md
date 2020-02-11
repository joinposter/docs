## products.get: Получить товар

> Пример получения всех товаров: 

```javascript
Poster.products.get([1, 2])
    .then((products) => {
        console.log(products);
    })
```

> Пример ответа:

```json
[
  {
    "id":1,
    "delete":1,
    "hidden":1,
    "fiscal":0,
    "fiscalProgram":0,
    "nodiscount":0,
    "parent":11,
    "sortOrder":999,
    "weightFlag":0,
    "workshop":1,
    "price":0,
    "cookingTime":0,
    "barcode":"",
    "picture":"",
    "color":"white",
    "taxType":0,
    "taxValue":0,
    "taxId":0,
    "taxName":""
  },
  {
    "id":2,
    "delete":1,
    "hidden":1,
    "fiscal":0,
    "fiscalProgram":0,
    "nodiscount":0,
    "parent":11,
    "sortOrder":999,
    "weightFlag":0,
    "workshop":1,
    "price":0,
    "cookingTime":0,
    "barcode":"",
    "picture":"",
    "color":"white",
    "taxType":0,
    "taxValue":0,
    "taxId":0,
    "taxName":""
  }
]
```

Метод возвращает информацию об одном или нескольких товарах

### Аргументы

Аргумент | Описание
-------- | --------
1-й, id | Id товара, или массив из id товараов

### Ответ

Функция возвращает Promise, который вернет объект с результатом выполнения.
В зависимости от первого аргумента вернется один объект или массив объектов типа [Product](/docs/api//docs/v3/pos/types/product) 

