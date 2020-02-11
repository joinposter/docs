## orders.addProduct: Add a Product or Dish to the Order

> Example how to add product without modification:

```javascript
Poster.orders.addProduct(1503219480866, {id: 1})
```

> Example how to add product with modification:

```javascript
Poster.orders.addProduct(1503219480866, {id: 1, modification: 1})
```

> Example how to add dish with modification:

```javascript
Poster.orders.addProduct(1503219480866, {
    id: 1, 
    modification: '[{"m":1,"a":1}]'
})
```

The method adds a product or dish to the order. The product is always added to the count of 1. To change the product count, use the [orders.changeProductCount](/en/docs/v3/pos/orders/orders-changeProductCount) method.

### Arguments

Argument | Description
-------- | -----------
1st, id | Order ID (unix-timestamp in milliseconds)
2nd, product | An object with the properties of a product being added to the order

The `product` object must contain the following properties

Property | Description
-------- | -----------
id | A mandatory parameter, product ID
modification | Modification ID. A mandatory parameter if the product has a modification. It can be a number if it’s a product or a line if it’s a dish with modifications.

### Response

The method returns `Promise`, the result of which is an object with the following properties:

Property | Description
-------- | -----------
order | An [Order](/en/docs/v3/pos/types/order)-type object, with an updated list of products

