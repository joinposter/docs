## orderClientChange: Update a Customer in the Order

```javascript
Poster.on('orderClientChange', (data) => {
	console.log(data);
})
```

The event is triggered by a customer being attached to the order or removed from it

### Response

As an argument, the `data` object comes to the handler with the following properties

Property | Value
-------- | -----
clientId | The ID of a customer that has been added to the order; `0` if the customer has been removed from the order
orderId | The ID of the order the customer has been attached to or detached from

