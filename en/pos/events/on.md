## on: Subscribe to event

> Request example:

```javascript
	Poster.on('beforeOrderClose', (data, next) => {
		alert('I was triggered before order has been closed');
		next();
	});
```

The method subscribes to [event](/en/docs/v3/pos/events/index).

### Arguments

Argument | Description
-------- | -----------
1st, event | Event name
2nd, callback | Handler function
