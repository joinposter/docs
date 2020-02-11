## orders.changeProductCount: Update the Product Count in the Order

> Example how to change product count 

```javascript
Poster.orders.changeProductCount(1503219480866, {id: 1, count: 2})
```

> Example how to delete product:

```javascript
Poster.orders.changeProductCount(1503219480866, {id: 1, count: 0})
```

The method updates the product count in the order. If you transfer a count of 0, the product is removed from the order. You can update the product count only if the product is already in the order. To add a product, use [orders.addProduct](/en/docs/v3/pos/orders/orders-addProduct)

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
count | New product count. It cannot be less than zero. If it is 0, the product is removed from the order.

### Response

The method returns `Promise`, the result of which is an object with the following properties:

Property | Description
-------- | -----------
order | An [Order](/en/docs/v3/pos/types/order)-type object, with an updated list of products

