## users.getActiveUser: Get Active User Data

> Request example:

```javascript
Poster.users.getActiveUser().then((user) => {
	if (!user) {
		return;
	}

	console.log(user.name);
});
```

The method gets active user data; the data type is [User](/en/docs/v3/pos/types/user).

### Response

The function returns Promise, which returns `false` if there is no user with such an ID or an object with the user data if any.

