## products.get: Get a product

> Request example: 

```javascript
Poster.products.get([1, 2])
    .then((products) => {
        console.log(products);
    })
```

> Response example:

```json
[
  {
    "id":1,
    "delete":1,
    "hidden":1,
    "fiscal":0,
    "fiscalProgram":0,
    "nodiscount":0,
    "parent":11,
    "sortOrder":999,
    "weightFlag":0,
    "workshop":1,
    "price":0,
    "cookingTime":0,
    "barcode":"",
    "picture":"",
    "color":"white",
    "taxType":0,
    "taxValue":0,
    "taxId":0,
    "taxName":""
  },
  {
    "id":2,
    "delete":1,
    "hidden":1,
    "fiscal":0,
    "fiscalProgram":0,
    "nodiscount":0,
    "parent":11,
    "sortOrder":999,
    "weightFlag":0,
    "workshop":1,
    "price":0,
    "cookingTime":0,
    "barcode":"",
    "picture":"",
    "color":"white",
    "taxType":0,
    "taxValue":0,
    "taxId":0,
    "taxName":""
  }
]
``` 


The method returns information about one or more products

### Arguments

Argument | Description
-------- | -----------
1st, id | Product ID or a product ID array

### Response

The function returns Promise, which returns an object with the execution result. Depending on the first argument, one object or an array of the [Product](/en/docs/v3/pos/types/product) type objects will be returned

