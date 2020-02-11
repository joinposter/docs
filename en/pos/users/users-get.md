## users.get: Get user data

> Request example:

```javascript
Poster.users.get(1).then((user) => {
	if ( ! user) {
		return;
	}

	console.log(user.name);
});
```

The method gets user data by the ID; the data type is [User](/en/docs/v3/pos/types/user).

### Arguments

Argument | Description
-------- | -----------
1st, id | User ID

### Response

The function returns Promise, which returns `false` if there is no user with such an ID or an object with the user data if any.

