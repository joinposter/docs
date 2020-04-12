## Событие разрыва соединения

Событие срабатывает в момент потери связи с внешним устройством. 
Даже при разрыве соединения вы можете отправлять сообщения методом [sendMessage](/docs/v3/devices/sendMessage). 
Они будут сохранены в очередь и будут доставлены после восстановления соединения.  


<!-- tabs:start -->

#### ** POS **

```javascript
Poster.on('deviceDisconnected', (data) => {
	console.log('Device disconnected', data.device);
})
```

### Ответ

В качестве аргумента в обработчик приходит объект `data` с такими свойствами

Свойство | Значение
-------- | --------
device | Устройство с которого пришло сообщение, тип [Device](/docs/v3/pos/types/device)


#### ** Android **


```kotlin
PosterTransport.onClose = { code, info, initByRemote ->
    Log.d(TAG, "Closed connection: $code $info $initByRemote")
}
```


Параметр | Описание
-------- | --------
Id | Номер причины по которой было разорвано соединение с устройством
info | Строка с дополнительной информацией
byRemote | Был ли вызван разрыв соединения устройством: `true` — устройством, `false` — ошибкой


<!-- tabs:start -->
