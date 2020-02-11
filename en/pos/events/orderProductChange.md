## orderProductChange: Update Order Products

```javascript
Poster.on('orderProductChange', (order) => {
	console.log(order);
})
```

> Response example:

```javascript
{
  "order":{
    "id":1506511064579,
    "dateStart":1506511064579,
    "dateClose":0,
    "datePrint":0,
    "status":1,
    "userId":3,
    "tableId":108,
    "orderName":25,
    "guestsCount":2,
    "products":{
      "0":{
        "id":4,
        "count":1,
        "printedNum":0,
        "productSum":60,
        "modificationHash":"",
        "taxId":"2",
        "taxValue":"20",
        "taxType":"2",
        "taxFiscal":1,
        "price":60
      }
    },
    "subtotal":60,
    "total":60,
    "discount":0,
    "clientId":7,
    "payType":"0",
    "payedSum":0,
    "payedCard":0,
    "payedCash":0,
    "payedThirdParty":0,
    "payedBonus":0,
    "loyaltyAppId":0,
    "parentId":0,
    "tipIncluded":0,
    "tipSum":0,
    "comment":""
  },
  "product":{
    "id":3,
    "count":0
  },
  "saveCallback":true
}
```

The event is triggered after a product has been updated in the order

### Response

As an argument, the `data` object comes to the handler with the following properties

Property | Value
-------- | -----
order | An updated [Order](/en/docs/v3/pos/types/order)-type order object
product | The object with an updated order

The `product`property contains the following properties

Property | Value
-------- | -----
id | Product ID
modification | Modification ID; if the product has no modification, it does not come
count | The new product count; if the value is 0, the product has been removed

