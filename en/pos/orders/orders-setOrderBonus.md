## orders.setOrderBonus: Set the order amount paid via an external System

> Request example: 

```javascript
Poster.orders.setOrderBonus(1503219480866, 100)
```

The method sets the order amount paid through your application. In addition to the point amount, the method will set the [Order](/en/docs/v3/pos/types/order) loyaltyAppId model property according to your application ID.

### Arguments

Argument | Description
-------- | -----------
1st, id | Order ID (unix-timestamp in milliseconds)
2nd, sum | Amount paid by points

