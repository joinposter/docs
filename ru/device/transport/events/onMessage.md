## onMessage: Событие сообщения


<!-- tabs:start -->

#### ** POS **

```javascript
Poster.on('deviceMessage', (data) => {
    console.log('New message', data.message);
	console.log('From device', data.device);
})
```

Событие срабатывает на полученное сообщение от устройства

### Ответ

В качестве аргумента в обработчик приходит объект `data` с такими свойствами

Свойство | Значение
-------- | --------
device | Устройство с которого пришло сообщение, тип [Device](/docs/v3/pos/types/device)
message | Сообщение, JSON объект


#### ** Android **

```kotlin
PosterTransport.onMessage = { device, message ->
    println("Message: $message\nFrom: ${device.ip}")                                 
}
```

Событие срабатывает на полученное сообщение от кассы

### Ответ

Аргумент | Значение
-------- | --------
device | Устройство с которого пришло сообщение. Тип [PosterDevice](#posterdevice).
message | JSON строка с сообщением от устройства


<!-- tabs:end -->
