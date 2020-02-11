# POS Settings: Settings

In the globally accessible `Poster.settings` object, the current account settings are available.

> Settings example:

```json

{
   "accountUrl":"dev-example",
   "country":"US",
   "currencyCodeIso":"USD",
   "currency":"$",
   "currencySymbol":"$",
   "lang":"ru",
   "spotId":1,
   "spotTabletId":1,
   "subnetMask":"192.168.1",
   "timezone":"America/Boston",
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

### Settings properties

Argument | Description
-------- | -----------
accountUrl | The subdomain the account is running on
applicationId | Your application ID
applicationName | Your application name; the roman type and lowercase numbers
country | The ISO country code of the account
currencyCodeIso | Digital currency code according to the ISO 4217 standard
currency | The abbreviated account currency name, for example, “UAH”, “RUB”
currencySymbol | Currency symbol, for example, “$,” “€”
lang | Account language: “ru”, “ua”, “en”, “pl”
spotId | Location ID in the account
spotTabletId | Register ID in the account
subnetMask | The first three numbers in the local IP address of the device, for example, “192.168.0”
timezone | Timezone, for example, “Europe/Kiev”
extras | Extras installed for the settings using the [application.setEntityExtras](/en/docs/v3/web/application/setEntityExtras) method
spotExtras | Extras installed for the location using the [application.setEntityExtras](/en/docs/v3/web/application/setEntityExtras) method
spotTabletExtras | Extras installed for the register using the [application.setEntityExtras](/en/docs/v3/web/application/setEntityExtras) method
usesTables | Flag if location uses tables, `true` — uses, `false` – not 
workshops | List of stations in location
