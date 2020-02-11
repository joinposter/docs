## devices.getAll: Получить все устройства

> Пример получения устройств Device Platform:

```javascript
let devices = await Poster.devices.getAll();

console.log(devices);

devices.forEach((device) => {
    device.sendMessage({ text: 'Hello' });
});
```

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
1й, filter | Объект содержит фильтры по которому вытягиваются устройства. Если не передавать фильтр то метод вернет устройства который работают с [Device Platform](/docs/v3/device/index).

Объект `filter` может содержать следующие параметры:

Параметр | Описание
-------- | --------
type | Тип устройства, возможные варианты: `printer` — термальные принтеры, `platform` — устройства которые работают с [Device Platform](/docs/v3/device/index)


### Ответ

Функция возвращает Promise, который вернет пустой массив, если нет подключенных устройств. 
Или массив объектов [Device](/docs/v3/pos/types/device), если есть хоть одно подключенное устройство.
