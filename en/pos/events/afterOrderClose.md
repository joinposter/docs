## afterOrderClose: After the Order Close

```javascript
Poster.on('afterOrderClose', (data) => {
	alert("Total payed " + data.order.total);
});
```

The event is triggered immediately after the order is paid.

### Arguments

Argument | Description
-------- | -----------
order | Order data; the [Order](/en/docs/v3/pos/types/order) data type

