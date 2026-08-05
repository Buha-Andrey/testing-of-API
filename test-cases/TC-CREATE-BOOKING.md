## Positive

### ID: SWAT-33970 - Title: Create booking: all fields with valid data

**Priority:** P0

**Precondition:**  -
 
**Test data:**   
Accept: application/json  
Content-Type: application/json  
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
  "additionalneeds": "/* string */"
}
```

**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send POST request  /booking/ with test data in request body  | Request is sent.  |
| 2  | Check code status  | HTTP Status 201 Created  |
| 3  | Check structure of response body | Response body contains expected keys.  |
| 4  | Check every value data type | Every value data type matches expected data type |

**Postcondition:**  
Delete the booking  

**Tags:** automated  

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>

##

<br>
<br>


### ID: SWAT-33971 - Title: POST /booking creates unique booking on each request

**Priority:** P2

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
  "additionalneeds": "/* string */"
}
```

**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send POST request  /booking/ with test data in request body  | Request is sent.  |
| 2  | Check code status  | HTTP Status 201 Created  |
| 3  | Check created ID  | Response body contains ID.  |
| 4  | Send the same POST request  /booking/ | Request is sent.   |
| 5  | Check code status  | HTTP Status 201 Created  |
| 6  | Check created ID  | Response body contains ID. ID of first request differs from ID of second request  |

**Postcondition:**  
Delete the bookings


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>

##

<br>
<br>


### ID: SWAT-33972 - Title: Create booking with header Accept: application/xml

**Priority:** P1

**Precondition:**  

**Test data:**  
Accept: application/xml  
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
  "additionalneeds": "/* string */"
}
```

**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send POST request  /booking/ with test data in request body  | Request is sent.  |
| 2  | Check code status  | HTTP Status 201 Created  |
| 3  | Check structure of response body | Response body is xml. Response body contains expected keys.   |
| 4  | Check every value data type | Every value data type matches expected data type  |

**Postcondition:**  
Delete the booking


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>

## Negative

<br>
<br>

### ID: SWAT-33973 - Title: Create booking without header Content-Type

**Priority:** P2

**Precondition:**  

**Test data:**  
Content-Type: (empty)  
  
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
  "additionalneeds": "/* string */"
}
```

**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send POST request  /booking/ with test data in request body  | Request is sent.  |
| 2  | Check code status  | HTTP Status 400 Bad Request  |
| 3  | Check structure of response body | Response body contains text `Bad Request`   |


**Postcondition:**  
Delete the booking


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>

##

<br>
<br>

### ID: SWAT-33974 - Title: Create booking without header Accept 

**Priority:** P2

**Precondition:**  

**Test data:**  
Accept:(empty)  
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
  "additionalneeds": "/* string */"
}
```

**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send POST request  /booking/ with test data in request body  | Request is sent.  |
| 2  | Check code status  | HTTP Status 400 Bad Request  |
| 3  | Check structure of response body | Response body contains text `Bad Request`   |

**Postcondition:**  
Delete the booking


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>

##

<br>
<br>

### ID: SWAT-33975 - Title: Create booking with invalid value of Content-Type header 

**Priority:** P2

**Precondition:**  

**Test data:**  
Content-Type : text/plain  
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
  "additionalneeds": "/* string */"
}
```

**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send POST request  /booking/ with test data in request body  | Request is sent.  |
| 2  | Check code status  | HTTP Status 400 Bad Request  |
| 3  | Check structure of response body | Response body contains text `Bad Request`   |

**Postcondition:**  
Delete the booking


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>

##

<br>
<br>

### ID: SWAT-33976 - Title: Create booking: firstname field validation

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
  "additionalneeds": "/* string */"
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
| 9  | Send POST request  /booking wit "firstname": { object } | Request is sent.  |
| 10 | Check code status  | HTTP Status 400 Bad Request  |


**Postcondition:**  


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>

##

<br>
<br>

### ID: SWAT-33977 - Title: Create booking: lastname field validation

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
  "additionalneeds": "/* string */"
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
| 9  | Send POST request  /booking wit "lastname": { object } | Request is sent.  |
| 10 | Check code status  | HTTP Status 400 Bad Request  |


**Postcondition:**  


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>

##

<br>
<br>

### ID: SWAT-33978 - Title: Create booking: totalprice field validation

**Priority:** P2

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
  "additionalneeds": "/* string */"
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
| 11 | Send POST request  /booking wit "totalprice": { object } | Request is sent.  |
| 12 | Check code status  | HTTP Status 400 Bad Request  |


**Postcondition:**  


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>

##

<br>
<br>

### ID: SWAT-33979 - Title: Create booking: depositpaid field validation

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
  "additionalneeds": "/* string */"
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
| 11 | Send POST request  /booking wit "depositpaid": { object } | Request is sent.  |
| 12 | Check code status  | HTTP Status 400 Bad Request  |


**Postcondition:**  


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>

##

<br>
<br>

### ID: SWAT-33980 - Title: Create booking: checkin field validation

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
  "additionalneeds": "/* string */"
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
| 11  | Send POST request  /booking without key-value pair checkin | Request is sent.  |
| 12 | Check code status  | HTTP Status 400 Bad Request  |
| 13 | Send POST request  /booking wit "checkin": { object } | Request is sent.  |
| 14 | Check code status  | HTTP Status 400 Bad Request  |


**Postcondition:**  


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>

##

<br>
<br>

### ID: SWAT-33981 - Title: Create booking: checkout field validation

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
  "additionalneeds": "/* string */"
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
| 11  | Send POST request  /booking without key-value pair checkout | Request is sent.  |
| 12 | Check code status  | HTTP Status 400 Bad Request  |
| 13 | Send POST request  /booking wit "checkout": { object } | Request is sent.  |
| 14 | Check code status  | HTTP Status 400 Bad Request  |


**Postcondition:**  


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>

##

<br>
<br>

### ID: SWAT-33982 - Title: Create booking with checkin date that is later than checkout date

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
  "additionalneeds": "/* string */"
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

<br>

##

<br>
<br>

### ID: SWAT-33983 - Title: Create booking with empty request body

**Priority:** P2

**Precondition:**  

**Test data:**  
 
**Request structure:**

Endpoint https://restful-booker.herokuapp.com/booking


**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send POST request  /booking  | Request is sent.  |
| 2  | Check code status  | HTTP Status 400 Bad Request |


**Postcondition:**  

**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii
