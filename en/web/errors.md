# errors: Error Codes

> Example of response:

```json
{  
  "error":{  
    "code":11,
    "message":"Bad access token"
  }
}
```

### Web API returns the following errors in it’s responses:

Error code | Description
---------- | -----------
0 | Success
10 | access_token is not specified
11 | Invalid access_token
12 | access_token expired
20 | The application is not authorized to call this method
32 | The ID doesn’t exist
34 | Absence of required properties
36 | The variable must be an array
38 | The name already exists
42 | The variable does not exist
44 | Error saving data
45 | Time is less than the order opening time
52 | The date range must be no more than 3 days
54 | Access denied
99 | Entity repetition
142 | Invalid verify
143 | Invalid application_id
153 | You are not allowed to make changes
154 | The name of the modifier must be unique
155 | The direct value of the parameter
701 | The field must be an integer
400 | Invalid request format, required data missing
404 | Record not found
700 | Rate restriction
4001 | Invalid currency


## **Order** section methods return additional errors:

Error code | Description
---------- | -----------
1 | Can't save data to database
41 | Product not found
42 | Product modification not found 
42 | Order not found
43 | Product in the order not found 
44 | Promotion not found
45 | Can't bind promotion to the order 
46 | Product count have to equal or greater then 0
47 | Promotion not found
49 | Guest not found
50 | Absence of required properties
60 | Location not found
88 | Total products sum not equal to payment sum
