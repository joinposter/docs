## returnFiscal: Fiscal return event 

> Subscription example:

```javascript
Poster.on('returnFiscal', (res) => {
    console.log(res);
});
```

> Response example:

```json
{
   "order":{
      "id":1544010298315,
      "dateStart":1544010298315,
      "dateClose":0,
      "datePrint":1544010308709,
      "status":2,
      "userId":40,
      "tableId":5,
      "orderName":77629,
      "guestsCount":3,
      "products":{
         "0":{
            "id":137,
            "count":1,
            "price":1180,
            "printedNum":0,
            "nodiscount":1,
            "taxId":1,
            "taxValue":0,
            "taxType":4,
            "taxFiscal":true,
            "roundSum":0
         }
      },
      "subtotal":1180,
      "total":1180,
      "discount":0,
      "clientId":0,
      "payType":"mix",
      "payedSum":0,
      "payedCard":0,
      "payedCash":1180,
      "payedBonus":0,
      "approvedBonus":0,
      "platformDiscount":0,
      "loyaltyAppId":0,
      "parentId":0,
      "tipIncluded":0,
      "tipSum":0,
      "roundSum":0,
      "printFiscal":1,
      "comment":""
   },
   "userId":40,
   "products":[
      {
         "product_id":137,
         "modification_id":0,
         "promotion_id":0,
         "count":1
      }
   ]
}
```

Event fires when user do fiscal return 

### Response

Parameter | Description
--------- | -----------
order | A [Order](/en/docs/v3/pos/types/order)-type order object with fiscal products
userId | Waiter Id who closed the order 
products | Fiscal products for return 
