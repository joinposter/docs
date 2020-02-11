## clients.create: Create a Customer on the Register

> Request example: 

```javascript
Poster.clients.create({
        client: {
            client_sex: 1,
            client_name: "Vladimir Ivanchenko", 
            client_groups_id_client: 1
        }
    })
    .then(function (client) {
        console.log('new client', client);
    });
```

> Response example:

```json
{
  "client":{
    "address":"0",
    "bonus":0,
    "discount":10,
    "firstname":"Vladimir",
    "groupId":1,
    "id":33,
    "lastname":"Ivanchenko",
    "loyaltyType":1,
    "phone":"",
    "totalPayedSum":0
  }
}
```

The method creates a new customer on the register and returns this customer’s [Client](/en/docs/v3/pos/types/client) model

### Arguments

Argument | Description
-------- | -----------
1st, request object | An object with the `client` property with customer data

The `client` property contains an object with such properties

Property | Description
-------- | -----------
client_name | A mandatory parameter, a line with the customer’s full name
client_groups_id_client | A mandatory parameter, the customer group ID
client_sex | Customer gender: 1—male, 2—female
country_phone_code | Number, customer country code, for example, 380 for Ukraine
phone | A line, customer phone number
email | A line, customer email
card_number | A line, customer card number
city | A line, customer city
address | A line, customer address
country | A line, customer country
comment | A line, a comment on the customer
birthday | A line, in the dd-MM-YYYY format

### Response

The function returns Promise, which returns an object with the `client` property or an error.

Property | Description
-------- | -----------
client | [Client](/en/docs/v3/pos/types/client)-type object

