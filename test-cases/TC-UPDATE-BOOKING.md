### ID: SWAT-31353 - Title: Update existing booking with firstname

**Priority:** P1

**Precondition:**
Authorize as admin 
Create booking with valid filled fields

**Test data:**  
firstname - Name  
 
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
  "bookingid": 1, // number
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
| 3  | Check structure  of response body | Response body contains expected keys.  |
| 4  | Check "firstname" key | "firstname" is changed to "Name" |

**Postcondition:**  
Delete the booking


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

---
