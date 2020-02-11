## device.setExtras: Установить дополнительный параметр устройству

> Пример запроса:

```javascript
let device = await Poster.devices.get("kd92kd6jqwe");

let result = await device.setExtras('workshops', ['1', '2']);

console.log('set extras result', result);
```

Метод получает устройство по Id, тип данных [Device](/docs/v3/pos/types/device).

### Аргументы

Аргумент | Описание
-------- | --------
1-й, name | Название дополнительного параметра

### Ответ

Метод возвращает `Promise` результат которого объект со следующими свойствами:

Параметр | Описание
-------- | --------
success | Результат выполнения операции: `true` – успех, `false` – ошибка
device | Устройство которому установили параметр, возвращается если `success=true`
message | Сообщение об ошибке, возвращается если `success=false`
