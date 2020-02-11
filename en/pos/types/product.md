## Product: Product

> Object example: 

```json
{
   "id":162,
   "delete":0,
   "hidden":0,
   "fiscal":0,
   "fiscalProgram":0,
   "nodiscount":0,
   "parent":0,
   "sortOrder":0,
   "weightFlag":0,
   "workshop":2,
   "price":10.5,
   "cookingTime":0,
   "barcode":"",
   "picture":"",
   "color":"white",
   "taxType":0,
   "taxValue":0,
   "taxId":0,
   "taxName":"",
   "extras":{

   }
}
```

### Properties

Property | Description
-------- | -----------
id | Product Id
delete | The status of the product being removed: 1—removed, 0—not removed
hidden | The status of the product being hidden: 1—hidden, 0—not hidden
fiscal | The status of the product being fiscal: 1—fiscal, 0—non-fiscal
fiscalProgram | Program number on a fiscal printer
nodiscount | The status of applying discounts to the product: 0—allowed to apply, 1—not allowed to apply
parent | Category ID
sortOrder | The number—the serial number of a product; it is used for sorting
weightFlag | The status of a product being sold by weight: 1—sold by weight, 0—not sold by weight
workshop | The ID of the station the product is attached to
price | The product cost in hryvnias/rubles
cookingTime | Cooking time
barcode | Product barcode
picture | Product image
color | Product icon color if there is no image
taxId | Tax ID, 0 — tax is not attached
taxType | Type of tax: 0 — tax type is not attached, 1 — VAT, 2 — turnover tax
taxValue | Tax percentage
taxName | Tax name
