## products.getFullName: Get a Product Full Name

> Request example:

```javascript
Poster.products.getFullName({
    id: 151, 
    modification: 59
}).then((prodName) => {
	console.log(prodName);
})
```

> Response example:

```json
{
  "id": 151, 
  "modification": 59, 
  "name": "Пицца (Маргарита)", 
  "modGroupName": ""
}
```


The method returns the product full name, including modifications

### Arguments

Argument | Description
-------- | -----------
1st | A product object, contains the following parameters

Parameter | Description
--------- | -----------
id | A mandatory parameter, the ID of a product the name of which you need to receive
modification | An optional parameter, the ID of the modification if it is a product or dish with a modifier

### Response

The function returns Promise, the results of which is an object or array of objects in the following format:

Parameter | Description
--------- | -----------
id | Product ID
modification | Modification ID
name | Full name of the product displayed in the order window
modGroupName | In case of a dish, it is the name of the modification groups; otherwise, it is empty

