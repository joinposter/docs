## device.isOnline: Проверить связь с устройством

> Пример запроса:

```javascript
let device = await Poster.devices.get("kd92kd6jqwe");

let status = await device.isOnline();

console.log('isOnline', status);
```

Метод возвращает статус подключенного устройства


### Ответ

Функция возвращает Promise, который вернет статус связи с устройством: `true` — онлайн, `false` – оффлайн
