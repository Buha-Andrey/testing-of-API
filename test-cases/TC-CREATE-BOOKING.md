### ID: SWAT-34353 - Title: Create booking with valid data

**Priority:** High

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


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

---
