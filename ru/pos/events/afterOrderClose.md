## afterOrderClose: после закрытия заказа

```javascript
Poster.on('afterOrderClose', (data) => {
	alert("Заказ на сумму " + data.order.total + " оплачен");
});
```

Событие срабатывает сразу после оплаты заказа

### Аргументы

Аргумент | Описание
-------- | -----------
order | Данные заказа, тип данных [Order](/docs/v3/pos/types/order)
