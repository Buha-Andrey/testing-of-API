### ID: SWAT-34353 - Title: Create booking with valid data

**Priority:** P0

**Precondition:**  

**Test data:**  
firstname - Brandon  
lastname - Sanderson  
totalprice - 100  
depositpaid - true  
checkin - 2025-01-01  
checkout - 2026-01-01  
additionalneeds - books  
 
**Request structure:**

Endpoint https://restful-booker.herokuapp.com/booking

Request Body
```json
{
    "firstname": "Brandon", 
    "lastname": "Sanderson", 
    "totalprice": 100, 
    "depositpaid": true, 
    "bookingdates": {
        "checkin": "2025-01-01",
        "checkout": "2026-01-01"
    }
    "additionalneeds" : "books"
}
```
Response Body
```json
{
    "bookingid": 2468, 
    "firstname": "Brandon", 
    "lastname": "Sanderson", 
    "totalprice": 100, 
    "depositpaid": true, 
    "bookingdates": {
        "checkin": "2025-01-01",
        "checkout": "2026-01-01"
    }
    "additionalneeds" : "books"
}
```

**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send POST request  /booking/ with test data in request body  | Request is sent.  |
| 2  | Check code status  | HTTP Status 201 Created  |
| 3  | Check struture of response body | Response body contains expected keys.  |
| 4  | Check every key type | Every key has expected type of value |

**Postcondition:**  
Delete the booking


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

---

### ID: SWAT-34354 - Title: Create booking with invalid firstname key

**Priority:** P2

**Precondition:**  

**Test data:**   
firstname -     
lastname - Sanderson   
totalprice - 100  
depositpaid - true  
checkin - 2025-01-01  
checkout - 2026-01-01  
additionalneeds - books  
 
**Request structure:**

Endpoint https://restful-booker.herokuapp.com/booking

Request Body
```json
{
    "firstname": "Brandon", 
    "lastname": "Sanderson", 
    "totalprice": 100, 
    "depositpaid": true, 
    "bookingdates": {
        "checkin": "2025-01-01",
        "checkout": "2026-01-01"
    }
    "additionalneeds" : "books"
}
```
Response Body
```json
{
    "bookingid": 2468, 
    "firstname": "Brandon", 
    "lastname": "Sanderson", 
    "totalprice": 100, 
    "depositpaid": true, 
    "bookingdates": {
        "checkin": "2025-01-01",
        "checkout": "2026-01-01"
    }
    "additionalneeds" : "books"
}
```

**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send POST request  /booking with "firstname": "" | Request is sent.  |
| 2  | Check code status  | HTTP Status 422 Unprocessable Entity  |
| 3  | Send POST request  /booking with "firstname": 100 | Request is sent.  |
| 4  | Check code status  | HTTP Status 400 Bad Request  |
| 5  | Send POST request  /booking with "firstname": null | Request is sent.  |
| 6  | Check code status  | HTTP Status 400 Bad Request  |
| 7  | Send POST request  /booking without key-value pair firstname | Request is sent.  |
| 8 | Check code status  | HTTP Status 400 Bad Request  |


**Postcondition:**  


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

---

### ID: SWAT-34355 - Title: Create booking with invalid lastname key

**Priority:** P2

**Precondition:**  

**Test data:**   
firstname - Brandon  
totalprice - 100    
depositpaid - true    
checkin - 2025-01-01    
checkout - 2026-01-01    
additionalneeds - books    
 
**Request structure:**

Endpoint https://restful-booker.herokuapp.com/booking

Request Body
```json
{
    "firstname": "Brandon", 
    "lastname": "Sanderson", 
    "totalprice": 100, 
    "depositpaid": true, 
    "bookingdates": {
        "checkin": "2025-01-01",
        "checkout": "2026-01-01"
    }
    "additionalneeds" : "books"
}
```
Response Body
```json
{
    "bookingid": 2468, 
    "firstname": "Brandon", 
    "lastname": "Sanderson", 
    "totalprice": 100, 
    "depositpaid": true, 
    "bookingdates": {
        "checkin": "2025-01-01",
        "checkout": "2026-01-01"
    }
    "additionalneeds" : "books"
}
```

**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send POST request  /booking with "lastname": "" | Request is sent.  |
| 2  | Check code status  | HTTP Status 422 Unprocessable Entity  |
| 3  | Send POST request  /booking with "lastname": 100 | Request is sent.  |
| 4  | Check code status  | HTTP Status 400 Bad Request  |
| 5  | Send POST request  /booking with "lastname": null | Request is sent.  |
| 6  | Check code status  | HTTP Status 400 Bad Request  |
| 7  | Send POST request  /booking without key-value pair lastname | Request is sent.  |
| 8 | Check code status  | HTTP Status 400 Bad Request  |


**Postcondition:**  


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

---
### ID: SWAT-34356 - Title: Create booking with invalid totalprice key

**Priority:** P1

**Precondition:**  

**Test data:**  
firstname - Brandon   
lastname - Sanderson   
totalprice -  
depositpaid - true   
checkin - 2025-01-01   
checkout - 2026-01-01   
additionalneeds - books   
  
**Request structure:**

Endpoint https://restful-booker.herokuapp.com/booking

Request Body
```json
{
    "firstname": "Brandon", 
    "lastname": "Sanderson", 
    "totalprice": 100, 
    "depositpaid": true, 
    "bookingdates": {
        "checkin": "2025-01-01",
        "checkout": "2026-01-01"
    }
    "additionalneeds" : "books"
}
```
Response Body
```json
{
    "bookingid": 2468, 
    "firstname": "Brandon", 
    "lastname": "Sanderson", 
    "totalprice": 100, 
    "depositpaid": true, 
    "bookingdates": {
        "checkin": "2025-01-01",
        "checkout": "2026-01-01"
    }
    "additionalneeds" : "books"
}
```

**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send POST request  /booking with "totalprice": -1 | Request is sent.  |
| 2  | Check code status  | HTTP Status 422 Unprocessable Entity  |
| 3  | Send POST request  /booking with "totalprice": 0 | Request is sent.  |
| 4  | Check code status  | HTTP Status 422 Unprocessable Entity  |
| 5  | Send POST request  /booking with "totalprice": "qwerty" | Request is sent.  |
| 6  | Check code status  | HTTP Status 400 Bad Request  |
| 7  | Send POST request  /booking with "totalprice": "100" | Request is sent.  |
| 8 | Check code status  | HTTP Status 400 Bad Request  |
| 9  | Send POST request  /booking without key-value pair totalprice | Request is sent.  |
| 10 | Check code status  | HTTP Status 400 Bad Request  |


**Postcondition:**  


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

---

### ID: SWAT-34357 - Title: Create booking with invalid depositpaid key

**Priority:** P2

**Precondition:**  

**Test data:**  
firstname - Brandon    
lastname - Sanderson    
totalprice - 100  
depositpaid -     
checkin - 2025-01-01    
checkout - 2026-01-01    
additionalneeds - books    
 
**Request structure:**

Endpoint https://restful-booker.herokuapp.com/booking

Request Body
```json
{
    "firstname": "Brandon", 
    "lastname": "Sanderson", 
    "totalprice": 100, 
    "depositpaid": true, 
    "bookingdates": {
        "checkin": "2025-01-01",
        "checkout": "2026-01-01"
    }
    "additionalneeds" : "books"
}
```
Response Body
```json
{
    "bookingid": 2468, 
    "firstname": "Brandon", 
    "lastname": "Sanderson", 
    "totalprice": 100, 
    "depositpaid": true, 
    "bookingdates": {
        "checkin": "2025-01-01",
        "checkout": "2026-01-01"
    }
    "additionalneeds" : "books"
}
```

**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send POST request  /booking with "depositpaid": -1 | Request is sent.  |
| 2  | Check code status  | HTTP Status 400 Bad Request  |
| 3  | Send POST request  /booking with "depositpaid": 0 | Request is sent.  |
| 4  | Check code status  | HTTP Status 400 Bad Request  |
| 5  | Send POST request  /booking with "depositpaid": "0" | Request is sent.  |
| 6  | Check code status  | HTTP Status 400 Bad Request  |
| 7  | Send POST request  /booking with "depositpaid": null | Request is sent.  |
| 8 | Check code status  | HTTP Status 400 Bad Request  |
| 9  | Send POST request  /booking without key-value pair depositpaid | Request is sent.  |
| 10 | Check code status  | HTTP Status 400 Bad Request  |


**Postcondition:**  


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

---

### ID: SWAT-34358 - Title: Create booking with invalid checkin key

**Priority:** P2

**Precondition:**  

**Test data:**  
firstname - Brandon   
lastname - Sanderson   
totalprice - 100  
depositpaid -  true  
checkin -  
checkout - 2026-01-01   
additionalneeds - books   
 
**Request structure:**

Endpoint https://restful-booker.herokuapp.com/booking

Request Body
```json
{
    "firstname": "Brandon", 
    "lastname": "Sanderson", 
    "totalprice": 100, 
    "depositpaid": true, 
    "bookingdates": {
        "checkin": "2025-01-01",
        "checkout": "2026-01-01"
    }
    "additionalneeds" : "books"
}
```
Response Body
```json
{
    "bookingid": 2468, 
    "firstname": "Brandon", 
    "lastname": "Sanderson", 
    "totalprice": 100, 
    "depositpaid": true, 
    "bookingdates": {
        "checkin": "2025-01-01",
        "checkout": "2026-01-01"
    }
    "additionalneeds" : "books"
}
```

**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send POST request  /booking with "checkin": 1 | Request is sent.  |
| 2  | Check code status  | HTTP Status 400 Bad Request  |
| 3  | Send POST request  /booking with "checkin": "qwerty" | Request is sent.  |
| 4  | Check code status  | HTTP Status 400 Bad Request  |
| 5  | Send POST request  /booking with "checkin": "2018" | Request is sent.  |
| 6  | Check code status  | HTTP Status 422 Unprocessable Entity  |
| 7  | Send POST request  /booking with "checkin": "2018-13-32" | Request is sent.  |
| 8 | Check code status  | HTTP Status 422 Unprocessable Entity  |
| 9  | Send POST request  /booking with "checkin": null | Request is sent.  |
| 10 | Check code status  | HTTP Status 400 Bad Request  |
| 9  | Send POST request  /booking without key-value pair checkin | Request is sent.  |
| 10 | Check code status  | HTTP Status 400 Bad Request  |


**Postcondition:**  


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

---

### ID: SWAT-34359 - Title: Create booking with invalid checkout key

**Priority:** P2

**Precondition:**  

**Test data:**  
firstname - Brandon  
lastname - Sanderson   
totalprice - 100  
depositpaid -  true  
checkin - 2026-01-01  
checkout -  
additionalneeds - books   
 
**Request structure:**

Endpoint https://restful-booker.herokuapp.com/booking

Request Body
```json
{
    "firstname": "Brandon", 
    "lastname": "Sanderson", 
    "totalprice": 100, 
    "depositpaid": true, 
    "bookingdates": {
        "checkin": "2025-01-01",
        "checkout": "2026-01-01"
    }
    "additionalneeds" : "books"
}
```
Response Body
```json
{
    "bookingid": 2468, 
    "firstname": "Brandon", 
    "lastname": "Sanderson", 
    "totalprice": 100, 
    "depositpaid": true, 
    "bookingdates": {
        "checkin": "2025-01-01",
        "checkout": "2026-01-01"
    }
    "additionalneeds" : "books"
}
```

**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send POST request  /booking with "checkout": 1 | Request is sent.  |
| 2  | Check code status  | HTTP Status 400 Bad Request  |
| 3  | Send POST request  /booking with "checkout": "qwerty" | Request is sent.  |
| 4  | Check code status  | HTTP Status 400 Bad Request  |
| 5  | Send POST request  /booking with "checkout": "2018" | Request is sent.  |
| 6  | Check code status  | HTTP Status 422 Unprocessable Entity  |
| 7  | Send POST request  /booking with "checkout": "2018-13-32" | Request is sent.  |
| 8 | Check code status  | HTTP Status 422 Unprocessable Entity  |
| 9  | Send POST request  /booking with "checkout": null | Request is sent.  |
| 10 | Check code status  | HTTP Status 400 Bad Request  |
| 9  | Send POST request  /booking without key-value pair checkout | Request is sent.  |
| 10 | Check code status  | HTTP Status 400 Bad Request  |


**Postcondition:**  


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

---

### ID: SWAT-34359 - Title: Create booking with checkin date that is later than checkout date

**Priority:** P2

**Precondition:**  

**Test data:**  
firstname - Brandon  
lastname - Sanderson  
totalprice - 100  
depositpaid -  true  
checkin - 2026-01-01  
checkout - 2025-01-01  
additionalneeds - books   
 
**Request structure:**

Endpoint https://restful-booker.herokuapp.com/booking

Request Body
```json
{
    "firstname": "Brandon", 
    "lastname": "Sanderson", 
    "totalprice": 100, 
    "depositpaid": true, 
    "bookingdates": {
        "checkin": "2025-01-01",
        "checkout": "2026-01-01"
    }
    "additionalneeds" : "books"
}
```
Response Body
```json
{
    "bookingid": 2468, 
    "firstname": "Brandon", 
    "lastname": "Sanderson", 
    "totalprice": 100, 
    "depositpaid": true, 
    "bookingdates": {
        "checkin": "2025-01-01",
        "checkout": "2026-01-01"
    }
    "additionalneeds" : "books"
}
```

**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send POST request  /booking  | Request is sent.  |
| 2  | Check code status  | HTTP Status 422 Unprocessable Entity  |



**Postcondition:**  


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

---

### ID: SWAT-34359 - Title: Create booking with empty request body

**Priority:** P2

**Precondition:**  

**Test data:**  
 
**Request structure:**

Endpoint https://restful-booker.herokuapp.com/booking

Request Body
```json
{
    "firstname": "Brandon", 
    "lastname": "Sanderson", 
    "totalprice": 100, 
    "depositpaid": true, 
    "bookingdates": {
        "checkin": "2025-01-01",
        "checkout": "2026-01-01"
    }
    "additionalneeds" : "books"
}
```
Response Body
```json
{
    "bookingid": 2468, 
    "firstname": "Brandon", 
    "lastname": "Sanderson", 
    "totalprice": 100, 
    "depositpaid": true, 
    "bookingdates": {
        "checkin": "2025-01-01",
        "checkout": "2026-01-01"
    }
    "additionalneeds" : "books"
}
```

**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send POST request  /booking  | Request is sent.  |
| 2  | Check code status  | HTTP Status 400 Bad Request |


**Postcondition:**  

**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii
