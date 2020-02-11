## orders.setOrderComment: Set an Order Comment

> Request example: 

```javascript
Poster.orders.setOrderComment(1503219480866, 'Order to go')
```

The method sets an order comment that will be available for employees to see in the order processing window and on the table plan. In addition, the comment will be printed in the receipt when the `Print an order comment` setting is enabled.

### Arguments

Argument | Description
-------- | -----------
1st, id | Order Id with unix-timestamp in milliseconds format
2nd, comment | Comment

