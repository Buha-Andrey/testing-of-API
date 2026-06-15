### ID: SWAT-33928 - Title: Authoriztion with valid credentials
**Priority:** High

**Precondition:** Server is active

**Test data:**

Request body 
```json
{
    "username" : "admin",
    "password" : "password123"
}
```

**Steps:**

|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send POST request https://restful-booker.herokuapp.com/auth | Request is sent  |
| 2  | Check code status  | HTTP Status 200 OK  |
| 3  | Check structure of response body  | JSON schema is correct: key and type |
| 4  | Check token  | Token value is not empty.   |


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

---

### ID: SWAT-33929 - Title: Authoriztion with wrong password

**Priority:** Medium

**Precondition:** -

**Test data:**

| username | password | 
|----------|----------|
| admin | wrongpassword | 

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
| 4  | Check authorization | Token is missed. Authorization is failed |


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

---

### ID: SWAT-33930 - Title: Authoriztion with wrong username

**Priority:** Medium

**Precondition:** -

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
| 4  | Check authorization | Token is missed. Authorization is failed |


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

---

### ID: SWAT-33931 - Title: Authoriztion with empty username

**Priority:** Medium

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
| 4  | Check authorization | Token is missed. Authorization is failed |


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

---

### ID: SWAT-33932 - Title: Authoriztion with empty password

**Priority:** Medium

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
| 4  | Check authorization | Token is missed. Authorization is failed |


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii


