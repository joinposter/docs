## Device: Устройство

> Пример устройства типа platform:

```json
{
    "id": "9fcb54d1f4a932d7",
    "name": "Kitchen Kit",
    "ip": "192.168.5.131",
    "appVersion": "2.0.2",
    "applicationId": 3,
    "status": 1,
    "icon": "https://dev.joinposter.com",
    "iconDevice": "https://dev.joinposter.com/public/apps/kitchen/icon-device.jpg",
    "connectionType": "lan"
}
```

> Пример устройства типа printer:

```json
{
    "ip": "192.168.5.63",
    "workshops": [0, 1],
    "paperWidth": 80,
    "useBell": false,
    "useCashDrawer": false,
    "useTextPrint": false,
    "textLineLength": 45,
    "connectionType": "lan",
    "id": "192.168.5.63",
    "name": "ESC/POS",
    "type": "printer"
}
```

### Свойства

Свойство | Описание
-------- | --------
id | Id устройства
name | Название устройства
ip | Ip адрес Устройства
type | Тип устройства: `platform` — устройство которое работает с [Device Platform](/docs/v3/device/index), `printer` — термальный принтер
connectionType | Тип подключения устройтва: `lan` – по локальной сети

В зависимости от поля `type` устройство может иметь дополнительные свойства

### type=platform

Свойство | Описание
-------- | --------
appVersion | Версия приложения подключенного девайса
applicationId | Id приложения которое подключило устройство
status | Статус подключенного устройства: 0 — новое устройство, 1 — заблокированно пользователем, 2 — подключено 
icon | Иконка приложения 
iconDevice | Картинка устройства  


### type=device

Свойство | Описание
-------- | --------
paperWidth | Ширина печатающей головки в мм
textLineLength | Максимальное кол-во символов помещающихся в одну строку
useBell | Звонить после печати: `true` — звонить, `false` — нет
useCashDrawer | Открывать кешбокс после печати: `true` — открывать, `false` — нет
useTextPrint | Использовать быструю печать: `true` — использовать, `false` — нет
workshops | Список из id цехов на которые печатает принтер. `0` — означает печать на чека, все цеха возвращаются в поле [Poster.settings.workshops](/docs/v3/pos/settings).  
