## deviceConnected: событие восстановления связи с устройством

```javascript
Poster.on('deviceConnected', (device) => {
	console.log('Device connected', device);
})
```

Событие срабатывает в момент восстановления связи с устройством 

### Ответ

Аргумент | Значение
-------- | --------
device | Устройство которое по пришло сообщение, тип [Device](/docs/v3/pos/types/device)
