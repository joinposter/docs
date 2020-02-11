# POS Settings: Настройки

В глобально доступном объекте `Poster.settings` доступны настройки текущего аккаунта.

> Пример настроек:

```json

{
   "accountUrl":"dev-example",
   "country":"RU",
   "currencyCodeIso":"RUB",
   "currency":"руб.",
   "currencySymbol":"<i class=\"icon-rouble\"></i>",
   "lang":"ru",
   "spotId":1,
   "spotTabletId":1,
   "subnetMask":"192.168.1",
   "timezone":"Europe/Berlin",
   "usesTables":true,
   "workshops":{
      "0":{
         "id":1,
         "name":"Bar",
         "printTickets":1
      },
      "1":{
         "id":2,
         "name":"Kitchen",
         "printTickets":1
      }
   },
   "applicationId":"110",
   "applicationName":"uds",
   "extras":{
      "token":"123aksldk0123kdadk1i31kd12kdas"
   },
   "spotExtras":{
      "groupId":"3"
   },
   "spotTabletExtras":{
      "tabletIp":"on"
   }
}

```

### Поля настроек

Аргумент | Описание
-------- | --------
accountUrl | Поддомен, на котором работает аккаунт
country | ISO-код страны аккаунта
currencyCodeIso | ISO-код валюты аккаунта
currency | Сокращенное написание валюты аккаунта, например «грн.», «руб»
currencySymbol | Символ валюты, например «$», «€». Для рубля указывется HTML иконка рубля.
lang | Язык аккаунта «ru», «ua», «en», «pl»
spotId | ID заведения в аккаунте
spotTabletId | ID кассы в аккаунте
subnetMask | Первые три числа в локальном IP-адресе устройсва, например «192.168.0»
usesTables | Включена ли карта столов, `true` — включен, `false` – выключена 
workshops | Список цехов в заведении
applicationId | ID вашего приложения
applicationName | Название вашего приложения, латиница и цифры в нижнем реестре
timezone | Часовой пояс, например «Europe/Kiev»
extras | extras установленные для аккаунта методом [application.setEntityExtras](/docs/v3/web/application/setEntityExtras)
spotExtras | extras установленные для заведения методом [application.setEntityExtras](/docs/v3/web/application/setEntityExtras)
spotTabletExtras | extras установленные для терминала методом [application.setEntityExtras](/docs/v3/web/application/setEntityExtras)
