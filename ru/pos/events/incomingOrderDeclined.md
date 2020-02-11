## incomingOrderDeclined: Онлайн-заказ отменили  

```javascript
Poster.on('incomingOrderDeclined', (data) => {
	console.log(data.incomingOrder);
});
```

Событие срабатывает когда кассир отменил онлайн-заказ

### Ответ

В качестве аргумента в обработчик приходит объект `data` с такими свойствами:

Свойство | Значение
-------- | --------
incomingOrder | Обьект онлайн-заказа типа [IncomingOrder](/docs/v3/pos/types/incomingOrder)

