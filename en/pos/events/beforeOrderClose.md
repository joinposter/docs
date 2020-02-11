## beforeOrderClose: Before the Order Checkout

> Subscription example:

```javascript
Poster.on('beforeOrderClose', (data, next) => {
	alert("Order total " + data.order.total);

	next();
});
```

> Example how to show button on checkout window:

```javascript
Poster.on('beforeOrderClose', (data, next) => {
	next({ payButton: 'My Pay Button' });
});
```



The event is triggered before the order is closed when the cashier clicks on the Pay button. 
As an argument, the data object comes with the order property—the data of the order to be closed.

The event is waiting for the next call, after which the thread of execution will return to the payment screen.

### Arguments

Argument | Description
-------- | -----------
order | Order data; the [Order](/en/docs/v3/pos/types/order) data type
next | Callback-function which have to be called to continue regular execution thread


Function `next` takes object with following properties

Property | Description
-------- | -----------
payButton | Title string for button on checkout window. By default, it is not transmitted. When user clicks this button [applicationIconClicked](/en/docs/v3/pos/events/applicationIconClicked) will be triggered.

