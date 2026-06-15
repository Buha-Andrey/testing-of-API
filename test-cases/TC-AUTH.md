## ID: SWAT-01 
## Title: Authoriztion with valid credentials
Priority: High

Precondition: -

Test data:
Request body 
```json
{
    "username" : "admin",
    "password" : "password123"
}
```

|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send POST request https://restful-booker.herokuapp.com/auth | Request is sent  |
| 2  | Check code status  | HTTP Status 200 OK  |
| 3  | Check structure of response body  | JSON schema is correct: key and type |
| 4  | Check token  | Token value is not empty.   |


Tags: automated

Additional info: https://restful-booker.herokuapp.com/apidoc/index.html
