## Получить все устройства


<!-- tabs:start -->

#### ** POS **

```javascript
// Получаем устройства 
let devices = await Poster.devices.getAll({ type: 'platform' });

console.log(devices);

devices.forEach((device) => {
    device.sendMessage({ text: 'Hello' });
});
```

Метод возвращает список всех подключенных устройств к кассе. Возвращает массив объектов типа [Device](/docs/v3/pos/types/device).

### Аргументы

Аргумент | Описание
-------- | --------
filter | Фильтр по типу устройства, чтобы получить внешние устройства у объекта должно быть свойство `type: 'platform'`

### Ответ

Функция возвращает Promise, который вернет пустой массив, если нет подключенных устройств. 
Или массив объектов [Device](/docs/v3/pos/types/device), если есть хоть одно подключенное устройство.


#### ** Android **


```kotlin
val connected = PosterTransport.connectedDevices
connected.forEach {
    it.sendMessage("{\"text\":\"Hello!\"}")
}
```

Свойство `connectedDevices` содержит список всех подключенных касс

<!-- tabs:end -->
