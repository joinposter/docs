## incomingOrderAccepted: Онлайн-заказ приняли 


```javascript
Poster.on('incomingOrderAccepted', (data) => {
	console.log(data.order, data.incomingOrder);
})
```

Событие срабатывает когда кассир принял онлайн-заказ. После принятия онлайн-заказ становится обычным заказом.

### Ответ

В качестве аргумента в обработчик приходит объект `data` с такими свойствами

Свойство | Значение
-------- | --------
incomingOrder | Обьект онлайн-заказа типа [IncomingOrder](/docs/v3/pos/types/incomingOrder)
order | Объект нового заказа типа [Order](/docs/v3/pos/types/order) который был создан из `incomingOrder`
