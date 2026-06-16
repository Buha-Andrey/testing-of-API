### ID: SWAT-34333 - Title: Get list of booking ids 

**Priority:** High

**Precondition:** -

**Test data:** -

**Request structure:**

Endpoint https://restful-booker.herokuapp.com/booking

Query parameters - 

Response Body
```json
[
    {
        "bookingid": 1
    },
    {
        "bookingid": 2
    },
/*  and so on */

]
```

**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send GET request /booking  | Request is sent.  |
| 2  | Check code status  | HTTP Status 200 OK  |
| 3  | Check response  | Body response is present JSON schema is correct: key and type |
| 4  | Check struture | "bookingid" in each element |
| 5  | Check bookingid type | "bookingid" is a number |


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

---
