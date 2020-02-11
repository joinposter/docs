## orderProductChange: изменения товаров зказа

```javascript
Poster.on('orderProductChange', (order) => {
	console.log(order);
})
```

> Пример ответа

```json
{
   "order":{
      "id":1506511064579,
      "dateStart":1506511064579,
      "dateClose":0,
      "datePrint":0,
      "status":1,
      "userId":3,
      "tableId":108,
      "orderName":25,
      "guestsCount":2,
      "products":{
         "0":{
            "id":4,
            "count":1,
            "printedNum":0,
            "productSum":60,
            "modificationHash":"",
            "taxId":"2",
            "taxValue":"20",
            "taxType":"2",
            "taxFiscal":1,
            "price":60
         }
      },
      "subtotal":60,
      "total":60,
      "discount":0,
      "clientId":7,
      "payType":"0",
      "payedSum":0,
      "payedCard":0,
      "payedCash":0,
      "payedThirdParty":0,
      "payedBonus":0,
      "loyaltyAppId":0,
      "parentId":0,
      "tipIncluded":0,
      "tipSum":0,
      "comment":""
   },
   "product":{
      "id":3,
      "count":0
   },
   "saveCallback":true
}
```

Событие срабатывает после изменения товара в заказе

### Ответ

В качестве аргумента в обработчик приходит объект `data` с такими свойствами

Свойство | Значение
-------- | --------
order | Объект обновленного заказа типа [Order](/docs/v3/pos/types/order) 
product | Объект с измененным заказом

Свойство `product` содержит следующие свойства

Свойство | Значение
-------- | --------
id | Id товара 
modification | Id модификации, если у товара нет модификации то не приходит
count | Новое кол-во товара, если значение равно 0, то товар удалили
