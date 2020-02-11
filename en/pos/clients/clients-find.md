## clients.find: Find a Customer on the Register

> Request example: 

```javascript
Poster.clients.find({
        searchVal: 'Vladimir'            
    })
    .then(function (result) {
        console.log('clients search', result);    
    })
```

> Response example:

```json
{
   "foundClients":[
      {
         "id":33,
         "firstname":"Vladimir",
         "lastname":"Ivanchenko",
         "loyaltyType":1,
         "discount":10,
         "hidden":0,
         "groupId":1,
         "cardNumber":"0",
         "bonus":0,
         "totalPayedSum":0,
         "city":"0",
         "address":"0",
         "comment":"0",
         "phone":""
      }
   ],
   "foundByCard":[

   ]
}
```

The method creates a new customer on the register. And returns the [Client](/en/docs/v3/pos/types/client) model of this customer

### Arguments

Argument | Description
-------- | -----------
1st, request object | An object with the `searchVal` property with customer data

Property | Description
-------- | -----------
searchVal | A mandatory parameter, the line we search for a customer by; the search is by the customer phone, name, last name, and card.

### Response

The function returns Promise, which returns an object with such properties.

Property | Description
-------- | -----------
foundClients | An array of the customers found; it contains [Client](/en/docs/v3/pos/types/client)-type objects
foundByCard | An array of the customers found with matches on the customer’s card; it contains [Client](/en/docs/v3/pos/types/client)-type objects

