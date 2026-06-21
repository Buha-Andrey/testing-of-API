### ID: SWAT-34333 - Title: Get list of booking ids 

**Priority:** P1

**Precondition:** -

**Test data:** -

**Request structure:**

Endpoint https://restful-booker.herokuapp.com/booking

Response Body
```json
[
    {
        "bookingid": 1  // number
    },
    {
        "bookingid": 2  // number
    },
/*  and so on */

]
```

**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send GET request /booking  | Request is sent.  |
| 2  | Check code status  | HTTP Status 200 OK  |
| 3  | Check struture of response body | Response body contains "bookingid" and its value. "bookingid" is shown in each element. |
| 4  | Check bookingid type | "bookingid" is a number |


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

---

### ID: SWAT-34334 - Title: Filter booking by firstname, lastname, checkin, checkout

**Priority:** P1

**Precondition:**  
Create booking     
firstname - RestfulBooker   
lastname - Test  
checkin - 2026-06-01      
checkout - 2026-06-17   


**Test data:** -

**Request structure:**

Endpoint https://restful-booker.herokuapp.com/booking

Query parameters ?firstname=RestfulBooker&lastname=Test&checkin=2026-06-01&checkout=2026-06-17 

Response Body
```json
[
    {
        "bookingid": 1  // number
    },
    {
        "bookingid": 2  // number
    },
/*  and so on */
]
```

**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send GET request /booking?firstname=RestfulBooker&lastname=Test&checkin=2026-06-01&checkout=2026-06-17   | Request is sent.  |
| 2  | Check code status  | HTTP Status 200 OK  |
| 3  | Check response body  | Response body contains "bookingid" and its value.  |


**Postcondition:**  
Delete test booking 

**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

---

### ID: SWAT-34335 - Title: Boundary value analysis of checkin date 
**Priority:** P1

**Precondition:**   
Create booking     
firstname - RestfulBooker   
lastname - Test  
checkin - 2026-01-01      


**Test data:** -

**Request structure:**

Endpoint https://restful-booker.herokuapp.com/booking

Query parameters ?firstname=RestfulBooker&lastname=Test&checkin=2026-01-01

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
| 1  | Send GET request /booking?firstname=RestfulBooker&lastname=Test&checkin=2026-01-01   | Request is sent.  |
| 2  | Check code status  | HTTP Status 200 OK  |
| 3  | Check response body  | Response body contains "bookingid" and its value.  |
| 4  | Send GET request /booking?firstname=RestfulBooker&lastname=Test&checkin=2025-12-31   | Request is sent.  |
| 2  | Check code status  | HTTP Status 200 OK  |
| 3  | Check response body  | Response body returns empty array.  |


**Postcondition:**  
Delete test booking 

**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

---

### ID: SWAT-34336 - Title: Boundary value analysis of checkout date
**Priority:** P1

**Precondition:**  
Create booking    
firstname - RestfulBooker  
lastname - Test  
checkout - 2025-12-31     


**Test data:** -

**Request structure:**

Endpoint https://restful-booker.herokuapp.com/booking

Query parameters ?firstname=RestfulBooker&lastname=Test&checkout=2025-12-31

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
| 1  | Send GET request /booking?firstname=RestfulBooker&lastname=Test&checkout=2025-12-31   | Request is sent.  |
| 2  | Check code status  | HTTP Status 200 OK  |
| 3  | Check response body  | Response body contains "bookingid" and its value.  |
| 4  | Send GET request /booking?firstname=RestfulBooker&lastname=Test&checkin=2026-01-01   | Request is sent.  |
| 2  | Check code status  | HTTP Status 200 OK  |
| 3  | Check response body  | Response body returns empty array.  |


**Postcondition:**  
Delete test booking 

**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

---
