## devices.getAll: Получить все принтеры

> Пример получения принтеров:

```javascript
let devices = await Poster.devices.getAll({ type: 'printer' });

console.log(devices);

devices.forEach((device) => {
    device.printText({ text: 'Hello World' });
});
```

Метод возвращает список всех подключенных устройств к кассе. Возвращает массив объектов типа [Device](/docs/v3/pos/types/device).

### Аргументы

Аргумент | Описание
-------- | --------
filter | Фильтр по типу устройства, чтобы получить принтеры у объекта должно быть свойство `type: 'printer'`

### Ответ

Функция возвращает Promise, который вернет пустой массив, если нет подключенных устройств. 
Или массив объектов [Device](/docs/v3/pos/types/device), если есть хоть одно подключенное устройство.
