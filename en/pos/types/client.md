## Client: Customer

> Object example:

```json
{
   "id":85,
   "firstname":"John",
   "lastname":"Smith",
   "loyaltyType":1,
   "discount":0,
   "hidden":0,
   "groupId":1,
   "cardNumber":"39237515928",
   "bonus":0,
   "totalPayedSum":0,
   "city":"",
   "address":"0",
   "comment":"",
   "email":"ivanchenko@gmail.com",
   "birthday":"1990-08-03",
   "phone":"+380682152264",
   "extras":{
   }
}
```

### Properties

Property | Description
-------- | -----------
id | Customer ID
address | Address
bonus | Amount of accumulated points
cardNumber | Loyalty card number
city | City
comment | Comment
discount | Percentage of discount or points accrued (depending on the loyaltyType property)
firstname | First name
groupId | Loyalty group ID the customer belongs to
hidden | 1—customer removed, 0—customer not removed
lastname | Last name
loyaltyType | 1—points-based loyalty system, 2—discount-based system
phone | Phone number
totalPayedSum | The total amount that the customer has spent at the location
birthday | Date of birth in `yyyy-MM-dd` format. If date does not specified default value is `0000-00-00` 
email | Email address
