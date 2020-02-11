## clients.get: Get Customer Data

> Request example:

```javascript
Poster.clients.get(1).then((client) => {
	if ( ! client) {
		return;
	}

	console.log(client.phone);
});
```


The method gets the customer data by the ID; the data type is [Client](/en/docs/v3/pos/types/client).

### Arguments

Argument | Description
-------- | -----------
1st, id | Customer ID

### Response

The function returns Promise, which returns `false` if there is no customer with such an ID or an object with the customer data if any.

### Customer parameters

Parameter | Description
--------- | -----------
client | [Client](/en/docs/v3/pos/types/client) type object

