## IncomingOrder: Онлайн-заказ


<details>
<summary>Показать пример онлайн-заказа</summary>


```json
{
   "id":118,
   "clientId":112,
   "type":1,
   "products":{
      "0":{
         "id":139,
         "incomingOrderId":"118",
         "count":1,
         "price":0.2,
         "createdAt":"2019-04-19 20:07:40",
         "ingredientId":"9",
         "productName":"Borjomi",
         "out":"0.0000000",
         "unit":"hg",
         "photo":"/upload/pos_cdb_7004/menu/product_1461595168_139.jpg",
         "menuCategoryId":"15",
         "starred":"0",
         "hidden":"0",
         "cost":"2000",
         "differentSpotsPrices":"0",
         "profit":"17600",
         "color":"white",
         "workshop":"1",
         "type":"3",
         "weightFlag":0,
         "delete":"0",
         "barcode":"",
         "sortOrder":"999",
         "productCode":"",
         "taxId":"0",
         "nodiscount":"0",
         "fiscal":"0",
         "productProductionDescription":null,
         "masterId":"0",
         "masterPrice":"18000",
         "cookingTime":"0",
         "modificationId":0
      }
   },
   "comment":"",
   "dateReservation":0,
   "duration":0,
   "guestCount":1,
   "tableId":0,
   "client":{
      "firstName":"Vladimir",
      "lastName":"",
      "phone":"380680000000",
      "email":"ivanchenko@joinposter.com",
      "sex":"",
      "birthday":"",
      "address":"",
      "clientGroupsId":4
   },
   "payment":{
      "id":"1",
      "incomingOrderId":"118",
      "type":1,
      "sum":0.2,
      "createdAt":2019
   },
   "sum":0.24
}
```
</details>


### Свойства

Свойство | Описание
-------- | --------
id | Id онлайн-заказа
clientId | Id [клиента](/docs/v3/pos/types/client), привязанного к заказу
comment | Комментарий
guestsCount | Количество гостей за столиком
type | 1 — онлайн-заказ, 2 — бронироване
sum | Сумма заказа
tableId | Id столика, на котором открыт заказ
products | Список товаров в заказе 


Внутри параметра `products` лежит объект, в каждом свойстве которого есть объект со следующими параметрами:

Свойство | Описание
-------- | --------
id | Id товара или тех. карты
count | Количество товара в заказе  
modificationId | Id модификатора 
price | Цена товара за единицу в гривнах или рублях. Приходит если цену указали в запросе, в других случаях приходит `null`. 


Если заказ оплатили приходит параметр `payments` внутри которого есть объект со следующими свойствами:

Свойство | Описание
-------- | --------
type | Признак, что была предварительная оплата: 0 — не была, 1 — была. По умолчанию принимает 0.
sum	| Сумма оплаты в копейках
currency | ISO код валюты оплаты, должен совпадать с валютой аккаунта, например: UAH — гривна, RUB — рубль, USD — доллар


Внутри параметра `client` есть объект со следующими свойствами:

Свойство | Описание
-------- | --------
firstName | Имя
lastName | Фамилия
phone | Номер телефона
email | Email адрес
sex | Пол
birthday | Дата рождения в формате `yyyy-MM-dd`. Если дата не указана будет передано значение `0000-00-00` 
address | Адрес
clientGroupId | Id группы лояльности, к которой принадлежит клиент
