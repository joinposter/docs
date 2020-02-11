## orderOpen: Create an Order

```javascript
Poster.on('orderOpen', (order) => {
	console.log(order);
})
```

The event is triggered after a new order is created

### Response

As an argument, the `data` object comes to the handler with the following properties

Property | Value
-------- | -----
order | A new [Order](/en/docs/v3/pos/types/order)-type order object

