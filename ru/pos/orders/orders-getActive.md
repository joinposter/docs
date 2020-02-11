## orders.getActive: получить текущий заказ

> Пример получения текущего заказа

```javascript
Poster.orders.getActive()
    .then(function (order) {
        console.log('active order', order);
    })
```

> Пример ответа 

```json
{
  "order":{
    "id":1508308514369,
    "dateStart":1508308514369,
    "dateClose":0,
    "datePrint":0,
    "status":1,
    "userId":4,
    "tableId":8,
    "orderName":14,
    "guestsCount":2,
    "products":{
      "0":{
        "id":7,
        "count":1,
        "price":0,
        "printedNum":0
      },
      "1":{
        "id":1,
        "count":1,
        "price":25,
        "printedNum":0
      }
    },
    "subtotal":25,
    "total":25,
    "discount":0,
    "clientId":0,
    "payType":"",
    "payedSum":0,
    "payedCard":0,
    "payedCash":0,
    "payedBonus":0,
    "loyaltyAppId":0,
    "parentId":0,
    "tipIncluded":0,
    "tipSum":0,
    "comment":""
  }
}
```

Метод получает модель текущего заказа, тип данных [Order](/docs/v3/pos/types/order)

### Ответ

Свойство | Описание
-------- | --------
order | Объект типа [Order](/docs/v3/pos/types/order), если пользователь находится на экране заказа или оплаты. На любом другом экране, свойства `order` не будет. 


