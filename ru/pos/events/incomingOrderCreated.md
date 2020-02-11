## incomingOrderCreated: Онлайн-заказ пришел на терминал  

```javascript
Poster.on('incomingOrderCreated', (data) => {
    console.log(data.incomingOrder);
});
```

Событие срабатывает когда создают новый онлайн-заказ по API методом [incomingOrders.createIncomingOrder](/docs/v3/web/incomingOrders/createIncomingOrder)

### Ответ

В качестве аргумента в обработчик приходит объект `data` с такими свойствами:

Свойство | Значение
-------- | --------
incomingOrder | Обьект онлайн-заказа типа [IncomingOrder](/docs/v3/pos/types/incomingOrder)
