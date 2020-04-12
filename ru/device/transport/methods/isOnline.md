## device.isOnline: Проверить связь с устройством


<!-- tabs:start -->

#### ** POS **

```javascript
let device = await Poster.devices.get("kd92kd6jqwe");

let status = await device.isOnline();

console.log('isOnline', status);
```

Метод возвращает статус подключенного устройства

### Ответ

Функция возвращает Promise, который вернет статус связи с устройством: `true` — онлайн, `false` – офлайн


#### ** Android **

```kotlin
val connected = PosterTransport.connectedDevices
connected.forEach {
    Log.d(TAG, "Device online: ${it.isOnline()}")
}
```

Метод возвращает статус подключенного устройства

### Ответ

Функция возвращает Promise, который вернет статус связи с устройством: `true` — онлайн, `false` – офлайн


<!-- tabs:end -->
