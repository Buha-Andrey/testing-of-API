### ID: SWAT-34343 - Title: Get booking with existing valid ID 

**Priority:** P1

**Precondition:**   
Create booking  
firstname - RestfulBooker    
lastname - Test   
checkin - 2026-06-01       
checkout - 2026-06-17   


**Test data:**   
Accept: application/json

**Request structure:**

Endpoint https://restful-booker.herokuapp.com/booking/id

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

<br>
<br>

---

<br>
<br>
<br>


### ID: SWAT-34343 - Title: Get booking with existing valid ID in xml format

**Priority:** P1

**Precondition:**   
Create booking  
firstname - RestfulBooker    
lastname - Test   
checkin - 2026-06-01       
checkout - 2026-06-17   


**Test data:**   
Accept: application/xml

**Request structure:**

Endpoint https://restful-booker.herokuapp.com/booking/id

Response Body
```xml
<booking>
    <firstname>/* string */</firstname>
    <lastname>/* string */</lastname>
    <totalprice>/* number */</totalprice>
    <depositpaid>/* boolean */</depositpaid>
    <bookingdates>
      <checkin>/* date,  CCYY-MM-DD */</checkin>
      <checkout>/* date,  CCYY-MM-DD */</checkout>
    </bookingdates>
    <additionalneeds>/* string */</additionalneeds>
  </booking>'
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

<br>
<br>

---

<br>
<br>
<br>

### ID: SWAT-34343 - Title: Get booking without header Accept  

**Priority:** P3

**Precondition:**   
Create booking  
firstname - RestfulBooker    
lastname - Test   
checkin - 2026-06-01       
checkout - 2026-06-17   


**Test data:**   
Accept: (empty)

**Request structure:**

Endpoint https://restful-booker.herokuapp.com/booking/id

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
  "additionalneeds": "/* string */"
}
```

**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send GET request  /booking/id  | Request is sent.  |
| 2  | Check code status  | HTTP Status 400 Bad Request |
| 3  | Check struture of response body | Response body contains expected keys.  |

**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>
<br>

---

<br>
<br>
<br>

### ID: SWAT-34343 - Title: Get booking with non-existent valid ID

**Priority:** P2

**Precondition:** -   

**Test data:**   
ID = 9999

**Request structure:**

Endpoint https://restful-booker.herokuapp.com/booking/id

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
  "additionalneeds": "/* string */"
}
```

**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send GET request  /booking/id  | Request is sent.  |
| 2  | Check code status  | HTTP Status 404 Not Found |
| 3  | Check struture of response body | Response body contains expected keys.  |

**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>
<br>

---

<br>
<br>
<br>

### ID: SWAT-34344 - Title: Get booking: ID parameter validation

**Priority:** P2

**Precondition:**  -

**Test data:** -

**Request structure:**

Endpoint https://restful-booker.herokuapp.com/booking/id


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


**Postcondition:**  -

**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

