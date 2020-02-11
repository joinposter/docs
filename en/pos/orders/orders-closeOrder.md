## orders.closeOrder: Closes open order

> Request example: 

```javascript
async function closeOrder() {
    const active = await Poster.orders.getActive();
    const res = await Poster.orders.closeOrder(active.order.id, {
        payment: { 
            cash: active.order.total 
        },
    });
    
    console.log(res);
}
```

> Successful response example:

```json
{ "result": "order has successfully closed" }
```


> Failed response example:

```json
{ "error": "can not find specific order" }
```

The method closes an open order on the register

### Arguments

Argument | Description
-------- | -----------
1st, orderId | The ID of an order you have to close
2nd, paymentDetails | The payment details about order


The `paymentDetails.payment` object must contain the following properties:

Property | Description
-------- | -----------
cash | Sum payed by cash
card | Sum payed by card


### Response

The function returns Promise, which returns an object with such properties

Property | Description
-------- | -----------
result | The operation result, if the field was returned, order was successfully closed
error | Returns only if error occurred
