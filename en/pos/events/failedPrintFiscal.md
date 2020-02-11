## failedPrintFiscal: Failed print fiscal receipt event 

> Subscription example:

```javascript
Poster.on('failedPrintFiscal', (res) => {
    console.log(res);
});
```

> Response example:

```json
{
   "order":{
      "id":1544009608209,
      "dateStart":1544009608209,
      "dateClose":0,
      "datePrint":0,
      "status":2,
      "userId":40,
      "tableId":5,
      "orderName":77624,
      "guestsCount":2,
      "products":{
         "0":{
            "id":309,
            "count":1,
            "price":280,
            "printedNum":0,
            "nodiscount":0,
            "taxId":1,
            "taxValue":6,
            "taxType":2,
            "taxFiscal":true,
            "roundSum":0
         }
      },
      "subtotal":280,
      "total":280,
      "discount":0,
      "clientId":0,
      "payType":"mix",
      "payedSum":0,
      "payedCard":0,
      "payedCash":280,
      "payedBonus":0,
      "approvedBonus":0,
      "platformDiscount":0,
      "loyaltyAppId":0,
      "parentId":0,
      "tipIncluded":0,
      "tipSum":0,
      "roundSum":0,
      "printFiscal":0,
      "comment":""
   },
   "userId":40,
   "errorCode":"050A",
   "errorText":"Forbidden tax"
}
```

Event fires when Poster can't print fiscal receipt 

### Response

Parameter | Description
--------- | -----------
order | A [Order](/en/docs/v3/pos/types/order)-type order object with fiscal products
userId | Waiter Id who closed the order 
errorCode | String with error code
errorText | String with error description
