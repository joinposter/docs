## Order: Заказ

> Пример объекта: 

```json
{
   "id":1533541148416,
   "dateStart":1533541148416,
   "dateClose":0,
   "datePrint":0,
   "status":1,
   "userId":1,
   "tableId":90,
   "orderName":330684,
   "guestsCount":2,
   "products":{
      "0":{
         "id":162,
         "count":2,
         "printedNum":4,
         "productSum":10.5,
         "price":10.5,
         "modificationHash":"",
         "taxId":"0",
         "taxValue":"0",
         "taxType":"0",
         "taxFiscal":0
      },
      "1":{
         "id":151,
         "count":1,
         "price":15,
         "printedNum":1,
         "modification":59
      },
      "2":{
         "id":150,
         "count":200,
         "price":0.2,
         "printedNum":0
      },
      "3":{
         "id":177,
         "count":1,
         "price":10,
         "printedNum":0,
         "modification":"[{\"m\":1,\"a\":1}]"
      }
   },
   "subtotal":86,
   "total":86,
   "discount":0,
   "clientId":108,
   "payType":"0",
   "payedSum":0,
   "payedCard":0,
   "payedCash":0,
   "payedThirdParty":0,
   "payedBonus":0,
   "approvedBonus":0,
   "platformDiscount":0,
   "loyaltyAppId":0,
   "parentId":0,
   "tipIncluded":0,
   "tipSum":0,
   "roundSum":0,
   "comment":"",
   "extras": {}
}
```

### Свойства

Свойство | Описание
-------- | --------
id | Id заказа
orderName | Id заказа в бек-офисе. Может быть пустым, пока заказ не засинхронизируется с сервером
incomingOrderId | Id входящего заказа, 0 - если обычный заказа 
clientId | Id [клиента](/docs/v3/pos/types/client), привязанного к заказу
comment | Комментарий
dateClose | Время закрытия заказа, Unix timestamp в миллисекундах
datePrint | Время последней печати пречека, Unix timestamp в миллисекундах
dateStart | Время открытия заказа, Unix timestamp в миллисекундах
discount | Процент скидки
guestsCount | Количество гостей за столиком
loyaltyAppId | Id приложения, методом оплаты которого закрывается бонусная часть оплаты заказа
parentId | Если заказ создан в процессе разделения другого заказа, указывает на родительский заказ
payType | Тип оплаты, `close` — если заказ был закрыт без оплаты, `mix` — во всех остальных случаях
payedBonus | Сумма, оплаченная бонусами
payedCard | Сумма, оплаченная платежной картой
payedCash | Сумма, оплаченная наличными
payedThirdParty | Сумма, оплаченная третьей стороной. Используется при оплате заказов в интернет-магазинах и агрегаторах
payedSum | Общая оплаченная сумма по заказу
approvedBonus | Сумма бонусов в грн\руб которую клиент использовал чтобы погасить часть стоимости заказа 
platformDiscount | Сумма скидки в грн\руб установленная сторонним приложением  
status | 1 — открытый, 2 — закрытый
subtotal | Сумма заказа до применения скидки
total | Сумма к оплате
tableId | Id столика, на котором открыт заказ
tipIncluded | Включен ли в сумму заказа процент за обслуживание
tipSum | Сумма процента за обслуживание
userId | Id кассира, к которому привязан заказ
extras | Список extras установлены для категории. Extras можно установить методом [application.setEntityExtras](https://dev.joinposter.com/docs/v3/web/application/setEntityExtras) или методом.
products | Список товаров в заказе. Каждый объект содержит следующее значение 

Внутри параметра `product` лежит объект, в каждом свойстве которого есть объект со следующими параметрами:

Свойство | Описание
-------- | --------
count | Количество товара в заказе  
id | Id товара или тех. карты
modification | Id модификации: Если товар — числовое значение id модификатора, если тех. карта — JSON модификации. Если товар без модификации передается `0` 
promotionId | Id акции
price | Цена товара за единицу в гривнах или рублях 
promotionPrice | Акционная цена товара 
printedNum | Количество товара которое было отправлено распечатано(отправлено) на кухню
taxId | Id налога в Poster, 0 — если товар без налога
taxType | Тип налога: 0 — налог не привзяан, 1 — налог с продаж, 2 — налог с оборота, 3 — НДС, 4 — без налога
taxValue | Процент налога
taxFiscal | Фискальность налога: 0 — не фискальный, 1 — фискальный
