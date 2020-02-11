## deviceMessage: событие сообщения от устройства

```javascript
Poster.on('deviceMessage', (device, message) => {
    console.log('New message', message);
	console.log('From device', device);
})
```

Событие срабатывает на полученное сообщение от устройства 

### Ответ

Аргумент | Значение
-------- | --------
device | Устройство с которого пришло сообщение, тип [Device](/docs/v3/pos/types/device)
message | Сообщение, типа json обьект
