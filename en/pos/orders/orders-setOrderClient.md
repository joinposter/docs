## orders.setOrderClient: Add a Customer to the Register Order

> Request example: 

```javascript
Poster.orders.setOrderClient(1509032509980, 30)
    .then(function (result) {
        console.log('client added', result);    
    })
```

> Response example:

```json
{
  "success":true
}
```

The method adds an existing customer to an open order on the register

### Arguments

Argument | Description
-------- | -----------
1st, orderId | The ID of an order you have to add a customer to
2nd, clientId | The ID of a customer being added to the order

### Response

The function returns Promise, which returns an object with such properties

Property | Description
-------- | -----------
success | The operation result: `true` — if the customer is added, `false` — if you failed to add a customer, for example, there is no customer or order with such an ID

