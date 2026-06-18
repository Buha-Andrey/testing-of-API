### ID: SWAT-34343 - Title: Get booking with existing valid ID 

**Priority:** High

**Precondition:**   
Create booking and get his ID   
firstname - RestfulBooker  
lastname - Test 
checkin - 2026-06-01     
checkout - 2026-06-17 


**Test data:** -

**Request structure:**

Endpoint https://restful-booker.herokuapp.com/booking

Response Body
```json
{
  "bookingid": 1, // number
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
| 1  | Send GET request  /booking/id  | Request is sent.  |
| 2  | Check code status  | HTTP Status 200 OK  |
| 3  | Check struture of response body | Response body contains expected keys.  |
| 4  | Check every key type | Every key has expected type of value |


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

---

### ID: SWAT-34344 - Title: Get booking with invalid ID

**Priority:** Low

**Precondition:**  


**Test data:** -

**Request structure:**

Endpoint https://restful-booker.herokuapp.com/booking


**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send GET request /booking/0  | Request is sent.  |
| 2  | Check code status  | HTTP Status 404 OK  |
| 3  | Check response body  | Error message is returned.  |
| 4  | Send GET request /booking/-10  | Request is sent.  |
| 5  | Check code status  | HTTP Status 404 OK  |
| 6  | Check response body  | Error message is returned.  |
| 7  | Send GET request /booking/qwerty  | Request is sent.  |
| 8  | Check code status  | HTTP Status 404 OK  |
| 9  | Check response body  | Error message is returned.  |


**Postcondition:**  
Delete test user "RestfulBooker Test" 

**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

