## userLogout: User Logout

```javascript
Poster.on('userLogout', (res, next) => {
	console.log(res);
	next();
})
```

The event is triggered after the user has logged out from the register. For example, at the waiter shift. After the event is triggered, the register waits for the platform to process the event and call the `next` function.

### Response

As an argument, the `data` object comes to the handler with the following properties

Property | Value
-------- | -----
user | The employee who has logged out from the register; a [User](/en/docs/v3/pos/types/user)-type object
next | a callback function that transmits the event processing to the register

