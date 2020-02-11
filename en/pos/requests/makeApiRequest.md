## makeApiRequest: Make an API Poster Request

> Request example:

```javascript
Poster.makeApiRequest('clients.getGroups', {
    method: 'get'

}, (groups) => {
	if (groups) {
		console.log(groups);
	}
});
```

The method makes an API Poster request. API requests can also be made through [Poster.makeRequest](/en/docs/v3/pos/requests/makeRequest), but `Poster.makeApiRequest` simplifies this procedure: it automatically inserts your application token and the current user account, makes `JSON.parse` of the response.

### Arguments

Argument | Description
-------- | -----------
1st, method | Method name from the Poster API
2nd, options | An object with request settings. All the [jQuery.ajax](http://api.jquery.com/jquery.ajax/) method parameters are available
3rd, callback | Response handler function

### Response

In `callback`, an object with the API response comes as the first argument or `false` if the request failed.

