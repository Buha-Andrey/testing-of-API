### ID: SWAT-33928 - Title: Authentication with valid credentials
**Priority:** P1

**Precondition:**   
Server is active  

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


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>
<br>

---

<br>
<br>
<br>


### ID: SWAT-33928 - Title: POST /auth generates unique token on each request
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
<br>

---

<br>
<br>
<br>

### ID: SWAT-33929 - Title: Authentication fails with incorrect password

**Priority:** P2

**Precondition:** 
-

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
<br>

---

<br>
<br>
<br>


### ID: SWAT-33930 - Title: Authentication fails with incorrect username

**Priority:** P2

**Precondition:**   
-  

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
<br>

---

<br>
<br>
<br>

### ID: SWAT-33931 - Title: Authentication  with empty username

**Priority:** P2

**Precondition:** -

**Test data:**

| username | password | 
|----------|----------|
| (empty) | password123 | 

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
| 2  | Check code status  | HTTP Status 400 Bad Request  |
| 3  | Check structure of response body  | JSON schema is correct: key and type |
| 4  | Check token | Token is missed. Authentication is failed |


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>
<br>

---

<br>
<br>
<br>

### ID: SWAT-33932 - Title: Authentication with empty password

**Priority:** P2

**Precondition:** -

**Test data:**

| username | password | 
|----------|----------|
| admin | (empty)  | 

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
| 2  | Check code status  | HTTP Status 400 Bad Request  |
| 3  | Check structure of response body  | JSON schema is correct: key and type |
| 4  | Check token | Token is missed. Authentication is failed |


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii


<br>
<br>

---

<br>
<br>
<br>

### ID: SWAT-33932 - Title: Authentication without header Content-Type

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

<br>
<br>

---

<br>
<br>
<br>

### ID: SWAT-33932 - Title: Authentication without header Content-Type

**Priority:** P2

**Precondition:** -

**Test data:**  
Content-Type : application/xml

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

