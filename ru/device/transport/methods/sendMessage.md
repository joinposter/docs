## sendMessage: Отправить сообщение устройству

Метод гарантированно отправляет сообщение на устройство. 
Если устройство offline то сообщение сохраняется в очередь и отправляется при восстановлении соединение. 
Если перезагрузить устройство, то очередь сообщений будет утеряна.
Сообщение приходит в метод [onMessage](/docs/v3/device/transport/events/onMessage)


<!-- tabs:start -->

#### ** POS **


```javascript
let devices = await Poster.devices.getAll({ type: 'platform' });

devices.forEach((device) => {
    const result = await device.sendMessage({ text: 'Hello' });
    console.log('send message result', result);
});
```

### Аргументы

Аргумент | Описание
-------- | --------
1-й, message | Сообщение в формате JS объекта 

### Ответ

Метод возвращает `Promise` результат которого объект со следующими свойствами:

Параметр | Описание
-------- | --------
success | Результат выполнения операции: `true` – успех, `false` – ошибка


#### ** Android **

```kotlin
PosterTransport.devices.forEach { 
    it.sendMessage("{\"text\":\"Hello!\"}")
}
```

### Аргументы

В качестве первого аргумента `msg` принимает JSON строку сообщения


<!-- tabs:end -->
