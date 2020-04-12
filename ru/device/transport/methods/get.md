## Получить устройство

> Пример запроса:

```javascript
let device = await Poster.devices.get("kd92kd6jqwe");

console.log(device);

if (device) {
    device.sendMessage({ text: 'Hello' });
}
```

Метод возвращает устройство по Id, тип данных [Device](/docs/v3/pos/types/device)

### Аргументы

Аргумент | Описание
-------- | --------
1-й, id | Id устройства

### Ответ

Функция возвращает Promise, который вернет `false`, если нет устройства с таким Id. Или объект [Device](/docs/v3/pos/types/device), если он есть
