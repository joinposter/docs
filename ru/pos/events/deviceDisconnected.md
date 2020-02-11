## deviceDisconnected: событие потери связи с устройством

```javascript
Poster.on('deviceDisconnected', (device) => {
	console.log('Device disconnected', device);
})
```

Событие срабатывает в момент потери связи с утройством. 
Вы все же можете отправлять сообщения устройству методом [device.sendMessage]() 

### Ответ

Аргумент | Значение
-------- | --------
device | Устройство с которого пришло сообщение, тип [Device](/docs/v3/pos/types/device)
