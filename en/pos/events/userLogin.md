## userLogin: User Authorization

```javascript
Poster.on('userLogin', (res) => {
	console.log(res);
})
```

The event is triggered after the user has logged on to the register. For example, after the PIN code is entered or at a quick waiter shift.

### Response

As an argument, the `data` object comes to the handler with the following properties

Property | Value
-------- | -----
user | The employee who has logged on to the register; a [User](/en/docs/v3/pos/types/user)-type object

