## Событие соединения с устройством 

<!-- tabs:start -->

#### ** POS **

```javascript
Poster.on('deviceConnected', (data) => {
    console.log('Device connected', data.device);
})
```

В качестве аргумента в обработчик приходит объект `data` с такими свойствами

Свойство | Значение
-------- | --------
device | Устройство с которого пришло сообщение, тип [Device](/docs/v3/pos/types/device)


#### ** Android **

```kotlin
PosterTransport.onOpen = {
    Log.d(TAG, "Library is ready")
}
```

Должен возвращать строку, в которой будет JSON объект с обязательным параметром action и значением "handshake".


<!-- tabs:end -->


