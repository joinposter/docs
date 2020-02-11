## Order: Order

> Object example: 

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
         "id":161,
         "count":0,
         "printedNum":2,
         "productSum":17,
         "price":17,
         "modificationHash":"",
         "taxId":"0",
         "taxValue":"0",
         "taxType":"0",
         "taxFiscal":0
      },
      "2":{
         "id":145,
         "count":0,
         "printedNum":1,
         "productSum":15,
         "price":15,
         "modificationHash":"",
         "taxId":"0",
         "taxValue":"0",
         "taxType":"0",
         "taxFiscal":0
      },
      "3":{
         "id":151,
         "count":1,
         "price":15,
         "printedNum":1,
         "modification":59
      },
      "4":{
         "id":150,
         "count":200,
         "price":0.2,
         "printedNum":0
      },
      "5":{
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
   "comment":""
}
```

### Properties

Property | Description
-------- | -----------
clientId | The ID of the [customer](/en/docs/v3/pos/types/client) attached to the order
comment | Comment
dateClose | Time of order closing, Unix timestamp in milliseconds
datePrint | Time of the latest print of the check, Unix timestamp in milliseconds
dateStart | Order opening time, Unix timestamp in milliseconds
discount | Discount
guestsCount | Seat count at the table
id | Order ID
loyaltyAppId | Application ID, the payment method of which closes the points-based part of the order payment
orderName | Order ID at the back office. It can be empty until the order gets synchronized with the server
parentId | If the order was created in the process of splitting another order, it indicates the parent order
payType | Payment type; `close` if the order was closed without payment, `mix`—in all other cases
payedBonus | Amount paid by points
payedCard | Amount paid by payment card
payedCash | Amount paid by cash
payedThirdParty | Amount paid by a third party. It is used when paying for orders in online stores and aggregators
payedSum | Total order amount paid
products | List of products in the order.
status | 1 — open, 2 — closed
subtotal | The order amount before applying the discount
total | Amount to be paid
tableId | The ID of the table an order is opened for
tipIncluded | The service fee being included in the order amount
tipSum | Service fee amount
userId | The ID of the cashier the order is attached to

Inside the `products` parameter, there is an object, each parameter has value which contains object with the following parameters:

Property | Description
-------- | -----------
count | Product count
id | Product ID 
modification | Modification ID: if this is product then id is numeric value of modification. If this is dish then id is JSON value of modification     
promotionId | Promotion ID
price | Product price per unit 
promotionPrice | Product promotional price 
printedNum | Product count that has been sent (printed) to the kitchen
taxId | Tax ID
taxType | Type of tax: 0 — tax is not attached, 1 — VAT, 2 — turnover tax
taxValue | Tax percentage
taxFiscal | Tax fiscality: 0 — non-fiscal, 1 — fiscal

