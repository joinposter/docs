## device.getExtras: Получить дополнительный параметр устройства

> Пример запроса:

```javascript
let device = await Poster.devices.get("kd92kd6jqwe");

let extras = await device.getExtras('workshops');

console.log('workshops extras', extras);
```

Метод получает данные установленные устройству методом [setExtras]()

### Аргументы

Аргумент | Описание
-------- | --------
1-й, name | Название дополнительного параметра

### Ответ

Функция возвращает Promise, который вернет `false`, если нет клиента с таким ID. Или объект с данными клиента, если он есть.

Параметр | Описание
-------- | --------
device | Объект типа [Device](/docs/v3/pos/types/device)
