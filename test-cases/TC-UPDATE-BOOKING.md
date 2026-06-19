### ID: SWAT-31353 - Title: Update booking: all fields with valid data

**Priority:** P1

**Precondition:**  
Authorize as admin  
Create booking with valid data  

**Test data:**    
firstname - Name  
lastname - Last  
totalprice - 1   
depositpaid - fasle  
checkin - 2028-01-01  
checkout - 2028-01-01  
additionalneeds - Wifi  
 
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
| 4  | Check value of keys | Value is changed to updated data |

**Postcondition:**  
Delete the booking


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>
<br>

---

<br>
<br>
<br>


### ID: SWAT-31354 - Title: Update booking with header Accept: application/xml

**Priority:** P1

**Precondition:**  
Authorize as admin   
Create booking with valid data  

**Test data:**    
Header Accept : "application/xml"

firstname - Name  
lastname - Last  
totalprice - 1  
depositpaid - fasle  
checkin - 2028-01-01  
checkout - 2028-01-01  
additionalneeds - Wifi  
 
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
```xml
<?xml version='1.0'?>
<booking>
    <firstname> /* string */ </firstname>
    <lastname> /* string */ </lastname>
    <totalprice> /* number */ </totalprice>
    <depositpaid> /* boolean  */ </depositpaid>
    <bookingdates>
        <checkin> /* date */ </checkin>
        <checkout> /* date */ </checkout>
    </bookingdates>
    <additionalneeds> /* string */ </additionalneeds>
</booking>
```

**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send PUT request  /booking/id with test data in request body  | Request is sent.  |
| 2  | Check code status  | HTTP Status 200 OK  |
| 3  | Check structure  of response body | Respons body is present in XML format. Response body contains expected keys.  |
| 4  | Check value of keys | Value is changed to updated data |

**Postcondition:**    
Delete the booking


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>
<br>

---

<br>
<br>
<br>


### ID: SWAT-31355 - Title: Update non-existent booking

**Priority:** P1

**Precondition:**  
Authorize as admin   

**Test data:**    
id = 9999  
 
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
| 2  | Check code status  | HTTP Status 404 Not Found  |
| 3  | Check structure  of response body | Response body contains expected keys.  |

**Postcondition:**  



**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>
<br>

---

<br>
<br>
<br>


### ID: SWAT-31356 - Title: Update booking without header Content-Type

**Priority:** P1

**Precondition:**  
Authorize as admin   
Create booking with valid data  

**Test data:**    
firstname - Name  
lastname - Last  
totalprice - 1  
depositpaid - fasle  
checkin - 2028-01-01  
checkout - 2028-01-01  
additionalneeds - Wifi  



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
| 2  | Check code status  | HTTP Status 400 Bad Request  |
| 3  | Check structure  of response body | Response body contains expected keys.  |


**Postcondition:**  
Delete booking


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>
<br>

---

<br>
<br>
<br>


### ID: SWAT-31357 - Title: Update booking without header Accept 

**Priority:** P1

**Precondition:**  
Authorize as admin   
Create booking with valid data  

**Test data:**    
firstname - Name  
lastname - Last  
totalprice - 1  
depositpaid - fasle  
checkin - 2028-01-01  
checkout - 2028-01-01  
additionalneeds - Wifi  



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
| 2  | Check code status  | HTTP Status 400 Bad Request  |
| 3  | Check structure  of response body | Response body contains expected keys.  |


**Postcondition:**  
Delete booking


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>
<br>

---

<br>
<br>
<br>


### ID: SWAT-31358 - Title: Update booking with invalid value of Content-Type header

**Priority:** P1

**Precondition:**  
Authorize as admin   
Create booking with valid data  

**Test data:**    
Content-Type : text/plain  

firstname - Name  
lastname - Last  
totalprice - 1  
depositpaid - fasle  
checkin - 2028-01-01  
checkout - 2028-01-01  
additionalneeds - Wifi  



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
| 2  | Check code status  | HTTP Status 400 Bad Request  |
| 3  | Check structure  of response body | Response body contains expected keys.  |


**Postcondition:**    
Delete booking  


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>
<br>

---

<br>
<br>
<br>


### ID: SWAT-31359 - Title: Update booking: firstname field validation

**Priority:** P2

**Precondition:**  
Authorize as admin   
Create booking with valid data  

**Test data:**    

firstname - ""  
firstname - 69  
firstname - null  



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
| 1  | Send PUT request  /booking/id without firstname field  | Request is sent.  |
| 2  | Check code status  | HTTP Status 400 Bad Request  |
| 3  | Send PUT request  /booking/id with  firstname = ""  | Request is sent.  |
| 4  | Check code status  | HTTP Status 422 Unprocessable Entity  |
| 5  | Send PUT request  /booking/id with  firstname = 69  | Request is sent.  |
| 6  | Check code status  | HTTP Status 400 Bad Request  |
| 7  | Send PUT request  /booking/id with  firstname = null  | Request is sent.  |
| 8  | Check code status  | HTTP Status 400 Bad Request  |



**Postcondition:**  
Delete booking


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>
<br>

---

<br>
<br>
<br>


### ID: SWAT-31360 - Title: Update booking: lastname  field validation

**Priority:** P2

**Precondition:**  
Authorize as admin   
Create booking with valid data  

**Test data:**    

lastname  - ""  
lastname  - 69  
lastname  - null  



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
| 1  | Send PUT request  /booking/id without lastname  field  | Request is sent.  |
| 2  | Check code status  | HTTP Status 400 Bad Request  |
| 3  | Send PUT request  /booking/id with  lastname  = ""  | Request is sent.  |
| 4  | Check code status  | HTTP Status 422 Unprocessable Entity  |
| 5  | Send PUT request  /booking/id with  lastname  = 69  | Request is sent.  |
| 6  | Check code status  | HTTP Status 400 Bad Request  |
| 7  | Send PUT request  /booking/id with  lastname  = null  | Request is sent.  |
| 8  | Check code status  | HTTP Status 400 Bad Request  |



**Postcondition:**  
Delete booking


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>
<br>

---

<br>
<br>
<br>


### ID: SWAT-31361 - Title: Update booking: totalprice field validation

**Priority:** P2

**Precondition:**  
Authorize as admin   
Create booking with valid data  

**Test data:**    

totalprice  - -1  
totalprice  - 0  
totalprice  - "qwerty"  



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
| 1  | Send PUT request  /booking/id without totalprice field  | Request is sent.  |
| 2  | Check code status  | HTTP Status 400 Bad Request  |
| 3  | Send PUT request  /booking/id with  totalprice  = 1  | Request is sent.  |
| 4  | Check code status  | HTTP Status 422 Unprocessable Entity  |
| 5  | Send PUT request  /booking/id with  totalprice  = 0  | Request is sent.  |
| 6  | Check code status  | HTTP Status 422 Unprocessable Entity  |
| 7  | Send PUT request  /booking/id with  totalprice  = "qwerty"  | Request is sent.  |
| 8  | Check code status  | HTTP Status 400 Bad Request  |



**Postcondition:**  
Delete booking


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>
<br>

---

<br>
<br>
<br>


### ID: SWAT-31362 - Title: Update booking: depositpaid field validation

**Priority:** P2

**Precondition:**  
Authorize as admin   
Create booking with valid data  

**Test data:**    

depositpaid  - -1  
depositpaid  - 0  
depositpaid  - "0"  
depositpaid - null  


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
| 1  | Send PUT request  /booking/id without depositpaid field  | Request is sent.  |
| 2  | Check code status  | HTTP Status 400 Bad Request  |
| 3  | Send PUT request  /booking/id with  depositpaid  = -1  | Request is sent.  |
| 4  | Check code status  | HTTP Status 400 Bad Request  |
| 5  | Send PUT request  /booking/id with  depositpaid  = 0  | Request is sent.  |
| 6  | Check code status  | HTTP Status 400 Bad Request  |
| 7  | Send PUT request  /booking/id with  depositpaid  = "0"  | Request is sent.  |
| 8  | Check code status  | HTTP Status 400 Bad Request  |
| 9  | Send PUT request  /booking/id with  depositpaid  = null  | Request is sent.  |
| 10  | Check code status  | HTTP Status 400 Bad Request  |


**Postcondition:**  
Delete booking


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>
<br>

---

<br>
<br>
<br>


### ID: SWAT-31362 - Title: Update booking: checkin field validation

**Priority:** P2

**Precondition:**  
Authorize as admin   
Create booking with valid data  

**Test data:**    

checkin - 1  
checkin - "qwerty"  
checkin - "2018"  
checkin - "2018-13-32"  
checkin - null  

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
| 1  | Send PUT request  /booking/id without checkin field  | Request is sent.  |
| 2  | Check code status  | HTTP Status 400 Bad Request  |
| 3  | Send PUT request  /booking/id with  checkin  = 1  | Request is sent.  |
| 4  | Check code status  | HTTP Status 400 Bad Request  |
| 5  | Send PUT request  /booking/id with  checkin  = "qwerty"  | Request is sent.  |
| 6  | Check code status  | HTTP Status 400 Bad Request  |
| 7  | Send PUT request  /booking/id with  checkin  = "2018"  | Request is sent.  |
| 8  | Check code status  | HTTP Status 422 Unprocessable Entity  |
| 9  | Send PUT request  /booking/id with  checkin  = "2018-13-32"  | Request is sent.  |
| 10  | Check code status  | HTTP Status 422 Unprocessable Entity  |
| 9  | Send PUT request  /booking/id with  checkin  = null  | Request is sent.  |
| 10  | Check code status  | HTTP Status 400 Bad Request  |

**Postcondition:**  
Delete booking


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>
<br>

---

<br>
<br>
<br>


### ID: SWAT-31363 - Title: Update booking: checkout field validation

**Priority:** P2

**Precondition:**  
Authorize as admin   
Create booking with valid data  

**Test data:**    

checkout - 1  
checkout - "qwerty"  
checkout - "2018"  
checkout - "2018-13-32"  
checkout - null  

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
| 1  | Send PUT request  /booking/id without checkout field  | Request is sent.  |
| 2  | Check code status  | HTTP Status 400 Bad Request  |
| 3  | Send PUT request  /booking/id with  checkout  = 1  | Request is sent.  |
| 4  | Check code status  | HTTP Status 400 Bad Request  |
| 5  | Send PUT request  /booking/id with  checkout  = "qwerty"  | Request is sent.  |
| 6  | Check code status  | HTTP Status 400 Bad Request  |
| 7  | Send PUT request  /booking/id with  checkout  = "2018"  | Request is sent.  |
| 8  | Check code status  | HTTP Status 422 Unprocessable Entity  |
| 9  | Send PUT request  /booking/id with  checkout  = "2018-13-32"  | Request is sent.  |
| 10  | Check code status  | HTTP Status 422 Unprocessable Entity  |
| 9  | Send PUT request  /booking/id with  checkout  = null  | Request is sent.  |
| 10  | Check code status  | HTTP Status 400 Bad Request  |

**Postcondition:**  
Delete booking


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>
<br>
---
<br>
<br>
<br>

