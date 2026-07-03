# Authentication (POST /auth)

## Positive

### ID: SWAT-33928 - Title: Authentication with valid credentials  
**Priority:** P1  

**Precondition:**   
Server is active  

**Test data:**  
username - admin  
password - password123  
Content-Type: application/json  

**Request structure:**  

Endpoint https://restful-booker.herokuapp.com/auth

Request body 
```json
{
    "username" : "/*string*/",
    "password" : "/*string*/"
}
```

Response Body

```json
{
    "token": "/*string*/"
}
```



**Steps:**

|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send POST request https://restful-booker.herokuapp.com/auth | Request is sent  |
| 2  | Check code status  | HTTP Status 200 OK  |
| 3  | Check structure of response body  | Response body contains expected key. |
| 4  | Check token  | Token value is not empty.   |
| 5  | Check Content-Type Header  | Content-Type is application/json   |


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>

##

<br>
<br>



### ID: SWAT-33929 - Title: POST /auth generates unique token on each request
**Priority:** P1

**Precondition:**   


**Test data:**  
username - admin  
password - password123  

**Request structure:**  

Endpoint https://restful-booker.herokuapp.com/auth

Request body 
```json
{
    "username" : "/*string*/",
    "password" : "/*string*/"
}
```

Response Body

```json
{
    "token": "/* string */"
}
```



**Steps:**

|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send POST request https://restful-booker.herokuapp.com/auth | Request is sent  |
| 2  | Check code status  | HTTP Status 200 OK  |
| 3  | Check token  | Token value is not empty.   |
| 4  | Send POST request https://restful-booker.herokuapp.com/auth | Request is sent  |
| 5  | Check code status  | HTTP Status 200 OK  |
| 6  | Is Token unique   | Token is unique |


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii


<br>

## Negative

<br>
<br>


### ID: SWAT-33930 - Title: Authentication fails with incorrect password

**Priority:** P2

**Precondition:** -

**Test data:**

| username | password | 
|----------|----------|
| admin | wrongpassword | 

**Request structure:**

Endpoint https://restful-booker.herokuapp.com/auth

Request body   
```json  
{
    "username" : "/*string*/",
    "password" : "/*string*/"
}
```
Response Body
```json
{
    "reason": "Bad credentials"
}
```

**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send POST request /auth | Request is sent.  |
| 2  | Check code status  | HTTP Status 401 Unauthorized  |
| 3  | Check structure of response body  | JSON schema is correct: key and type |
| 4  | Check authorization | Token is missed. Authentication is failed |


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii


<br>

##

<br>
<br>


### ID: SWAT-33931 - Title: Authentication fails with incorrect username

**Priority:** P2

**Precondition:**  -  

**Test data:**

| username | password | 
|----------|----------|
| invaliduser | password123 | 

**Request structure:**

Endpoint https://restful-booker.herokuapp.com/auth

Request Body
```json
{
    "username" : "string" ,
    "password" : "string"
}
```
Response Body
```json
{
    "reason": "Bad credentials"
}
```

**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send POST request /auth | Request is sent.  |
| 2  | Check code status  | HTTP Status 401 Unauthorized  |
| 3  | Check structure of response body  | JSON schema is correct: key and type |
| 4  | Check token | Token is missed. Authentication is failed |


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>

##

<br>
<br>

### ID: SWAT-33932 - Title: Authentication: username field validation

**Priority:** P2

**Precondition:** -

**Test data:**

| username | password | 
|----------|----------|
| - | password123 | 

**Request structure:**

Endpoint https://restful-booker.herokuapp.com/auth

Request Body
```json
{
    "username" : "string" ,
    "password" : "string"
}
```
Response Body
```json
{
    "reason": "Bad credentials"
}
```

**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send POST request  /auth with "username": "" | Request is sent.  |
| 2  | Check code status  | HTTP Status 401 Unauthorized  |
| 3  | Send POST request  /auth with "username": 100 | Request is sent.  |
| 4  | Check code status  | HTTP Status 400 Bad Request  |
| 5  | Send POST request  /auth with "username": null | Request is sent.  |
| 6  | Check code status  | HTTP Status 400 Bad Request  |
| 7  | Send POST request  /auth without key-value pair username | Request is sent.  |
| 8 | Check code status  | HTTP Status 400 Bad Request  |



**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>

##

<br>
<br>

### ID: SWAT-33933 - Title: Authentication: password field validation 

**Priority:** P2

**Precondition:** -

**Test data:**

| username | password | 
|----------|----------|
| admin |  - | 

**Request structure:**

Endpoint https://restful-booker.herokuapp.com/auth

Request Body
```json
{
    "username" : "string" ,
    "password" : "string"
}
```
Response Body
```json
{
    "reason": "Bad credentials"
}
```

**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send POST request  /auth with "password": "" | Request is sent.  |
| 2  | Check code status  | HTTP Status 401 Unauthorized  |
| 3  | Send POST request  /auth with "password": 100 | Request is sent.  |
| 4  | Check code status  | HTTP Status 400 Bad Request  |
| 5  | Send POST request  /auth with "password": null | Request is sent.  |
| 6  | Check code status  | HTTP Status 400 Bad Request  |
| 7  | Send POST request  /auth without key-value pair password | Request is sent.  |
| 8 | Check code status  | HTTP Status 400 Bad Request  |


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii


<br>

##

<br>
<br>

### ID: SWAT-33934 - Title: Authentication without header Content-Type

**Priority:** P2

**Precondition:** -

**Test data:**  
Content-Type : (empty)

| username | password | 
|----------|----------|
| admin | password123  | 

**Request structure:**

Endpoint https://restful-booker.herokuapp.com/auth

Request Body
```json
{
    "username" : "string" ,
    "password" : "string"
}
```


**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send POST request /auth | Request is sent.  |
| 2  | Check code status  | HTTP Status 400 Bad Request  |
| 3  | Check structure of response body  | JSON schema is correct: key and type |



**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

# Authorization (Token Usage)

## Positive

### ID: SWAT-33936 - Title: Authorization: PUT with valid token  

**Priority:** P1

**Precondition:**  
Authorize as admin  and save token  
Create booking with valid data  and save booking ID  

**Test data:**    
firstname - Name  
lastname - Last  
totalprice - 1   
depositpaid - fasle  
checkin - 2028-01-01  
checkout - 2028-01-01  
additionalneeds - Wifi  
Cookie: token={{token}}  
 
**Request structure:**

Endpoint https://restful-booker.herokuapp.com/booking/id

Request Body
```json
{
  "firstname": "/* string */",
  "lastname": "/* string */",
  "totalprice": 100,  // number
  "depositpaid": true,  // boolean
  "bookingdates": {
    "checkin": "2026-06-20",  // date,  CCYY-MM-DD
    "checkout": "2026-06-25"  // date,  CCYY-MM-DD
  },
  "additionalneeds": "/* string */"
}
```

Response Body
```json
{
  "firstname": "/* string */",
  "lastname": "/* string */",
  "totalprice": 100,  // number
  "depositpaid": true,  // boolean
  "bookingdates": {
    "checkin": "2026-06-20",  // date,  CCYY-MM-DD
    "checkout": "2026-06-25"  // date,  CCYY-MM-DD
  },
  "additionalneeds": "/* string, */"
}
```

**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send PUT request  /booking/id with test data in request body  | Request is sent.  |
| 2  | Check code status  | HTTP Status 200 OK  |
| 3  | Check response body  | Data is updated  |


**Postcondition:**  
Delete the booking


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>

##

<br>
<br>

### ID: SWAT-33937 - Title: PATCH with valid token  

**Priority:** P1

**Precondition:**  
Authorize as admin  
Create booking with valid data  

**Test data:**    
firstname - Name  
 
**Request structure:**

Endpoint https://restful-booker.herokuapp.com/booking/id

Request Body
```json
{
  "firstname": "/* string */",
}
```

Response Body
```json
{
  "firstname": "/* string */",
  "lastname": "/* string */",
  "totalprice": 100,  // number
  "depositpaid": true,  // boolean
  "bookingdates": {
    "checkin": "2026-06-20",  // date,  CCYY-MM-DD
    "checkout": "2026-06-25"  // date,  CCYY-MM-DD
  },
  "additionalneeds": "/* string, */"
}
```

**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send PATCH request  /booking/id with test data in request body  | Request is sent.  |
| 2  | Check code status  | HTTP Status 200 OK  |
| 3  | Check response body  | Data is updated  |


**Postcondition:**  
Delete the booking


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>

##

<br>
<br>

### ID: SWAT-33938 - Title: DELETE  with valid token  

**Priority:** P1

**Precondition:**  
Authorize as admin  
Create booking with valid data  

**Test data:**    
 
**Request structure:**

Endpoint https://restful-booker.herokuapp.com/booking/id



**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send DELETE  request  /booking/id with test data in request body  | Request is sent.  |
| 2  | Check code status  | HTTP Status 204 No Content  |
| 3  | Check response body  | Booking is deleted  |


**Postcondition:**  -

**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>

## Negative

<br>
<br>

### ID: SWAT-33939 - Title: PUT without token 

**Priority:** P1

**Precondition:**  
Create booking with valid data  

**Test data:**    
firstname - Name  
lastname - Last  
totalprice - 1   
depositpaid - fasle  
checkin - 2028-01-01  
checkout - 2028-01-01  
additionalneeds - Wifi  
 
**Request structure:**

Endpoint https://restful-booker.herokuapp.com/booking/id

Request Body
```json
{
  "firstname": "/* string */",
  "lastname": "/* string */",
  "totalprice": 100,  // number
  "depositpaid": true,  // boolean
  "bookingdates": {
    "checkin": "2026-06-20",  // date,  CCYY-MM-DD
    "checkout": "2026-06-25"  // date,  CCYY-MM-DD
  },
  "additionalneeds": "/* string */"
}
```


**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send PUT request  /booking/id with test data in request body  | Request is sent.  |
| 2  | Check code status  | HTTP Status 403 Forbidden  |


**Postcondition:**  
Delete the booking


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>

## 

<br>
<br>

### ID: SWAT-33940 - Title: PATCH without token 

**Priority:** P1

**Precondition:**  
Create booking with valid data  

**Test data:**    
firstname - Name  

 
**Request structure:**

Endpoint https://restful-booker.herokuapp.com/booking/id

Request Body
```json
{
  "firstname": "/* string */",
}
```




**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send PATCH request  /booking/id with test data in request body  | Request is sent.  |
| 2  | Check code status  | HTTP Status 403 Forbidden  |


**Postcondition:**  
Delete the booking


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>

## 

<br>
<br>

### ID: SWAT-33941 - Title: DELETE without token 

**Priority:** P1

**Precondition:**  
Create booking with valid data  

**Test data:**    -
 
**Request structure:**

Endpoint https://restful-booker.herokuapp.com/booking/id



**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send DELETE request  /booking/id with test data in request body  | Request is sent.  |
| 2  | Check code status  | HTTP Status 403 Forbidden  |


**Postcondition:**  
Delete the booking


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii


<br>

## 

<br>
<br>

### ID: SWAT-33942 - Title: PUT with invalid token

**Priority:** P1

**Precondition:**  
Create booking with valid data  

**Test data:**   
token = wrong-token
 
**Request structure:**

Endpoint https://restful-booker.herokuapp.com/booking/id


**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send PUT request  /booking/id with test data in request body  | Request is sent.  |
| 2  | Check code status  | HTTP Status 403 Forbidden  |


**Postcondition:**  -

**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>

## 

<br>
<br>

### ID: SWAT-33943 - Title: PATCH with invalid token

**Priority:** P1

**Precondition:**  
Create booking with valid data  

**Test data:**   
token = wrong-token
 
**Request structure:**

Endpoint https://restful-booker.herokuapp.com/booking/id


**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send PATCH  request  /booking/id with test data in request body  | Request is sent.  |
| 2  | Check code status  | HTTP Status 403 Forbidden  |


**Postcondition:**  -

**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>

## 

<br>
<br>

### ID: SWAT-33944 - Title: DELETE with invalid token

**Priority:** P1

**Precondition:**  
Create booking with valid data  

**Test data:**   
token = wrong-token
 
**Request structure:**

Endpoint https://restful-booker.herokuapp.com/booking/id


**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send DELETE request  /booking/id with test data in request body  | Request is sent.  |
| 2  | Check code status  | HTTP Status 403 Forbidden  |


**Postcondition:**  -

**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii
