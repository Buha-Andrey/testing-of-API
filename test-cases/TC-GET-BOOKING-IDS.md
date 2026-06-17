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
| 3  | Check response  | Body response is present  |
| 4  | Check struture | "bookingid" is shown in each element |
| 5  | Check bookingid type | "bookingid" is a number |


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

---

### ID: SWAT-34333 - Title: Get booking id of test user

**Priority:** High

**Precondition:** 
Create user with next parameters  
firstname - RestfulBooker 
lastname - Test
checkin - 2026-06-01    
checkout - 2026-06-17 


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
| 3  | Check response  | Body response is present  |
| 4  | Check struture | "bookingid" is shown in each element |
| 5  | Check bookingid type | "bookingid" is a number |


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

---
