## Positive

### ID: SWAT-34010 - Title: Partial update: firstname field with valid data

**Priority:** P1

**Precondition:**  
Authorize as admin  
Create booking with valid data  

**Test data:**    
Content-Type: application/json  
Accept: application/json  
firstname - Name  

 
**Request structure:**

Endpoint https://restful-booker.herokuapp.com/booking/id

Request Body
```json
{
  "firstname": "/* string */"
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
  "additionalneeds": "/* string */"
}
```

**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send PATCH request  /booking/id with test data in request body  | Request is sent.  |
| 2  | Check code status  | HTTP Status 200 OK  |
| 3  | Check structure  of response body | Response body contains expected keys.  |
| 4  | Check value of keys | Value is changed to updated data |

**Postcondition:**  
Delete the booking


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>

##

<br>
<br>

 ### ID: SWAT-34011 - Title: Partial update: lastname field with valid data

**Priority:** P1

**Precondition:**  
Authorize as admin  
Create booking with valid data  

**Test data:**    
Content-Type: application/json  
Accept: application/json  
lastname - Last  
 
**Request structure:**

Endpoint https://restful-booker.herokuapp.com/booking/id

Request Body
```json
{
   "lastname": "/* string */"
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
  "additionalneeds": "/* string */"
}
```

**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send PATCH request /booking/id with test data in request body  | Request is sent.  |
| 2  | Check code status  | HTTP Status 200 OK  |
| 3  | Check structure  of response body | Response body contains expected keys.  |
| 4  | Check value of keys | Value is changed to updated data |

**Postcondition:**  
Delete the booking


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>

##

<br>
<br>

### ID: SWAT-34012 - Title: Partial update: totalprice field with valid data

**Priority:** P1

**Precondition:**  
Authorize as admin  
Create booking with valid data  

**Test data:**    
Content-Type: application/json  
Accept: application/json  
totalprice - 1   
totalprice - 2.5   
 
**Request structure:**

Endpoint https://restful-booker.herokuapp.com/booking/id

Request Body
```json
{
  "totalprice": 100  // number
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
  "additionalneeds": "/* string */"
}
```

**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send PATCH request /booking/id with totalprice = integer number in request body  | Request is sent.  |
| 2  | Check code status  | HTTP Status 200 OK  |
| 3  | Check structure  of response body | Response body contains expected keys.  |
| 4  | Check value of keys | Value is changed to updated data |
| 5  | Send PATCH request /booking/id with totalprice = float number in request body  | Request is sent.  |
| 6  | Check code status  | HTTP Status 200 OK  |
| 7  | Check structure  of response body | Response body contains expected keys.  |
| 8  | Check value of keys | Value is changed to updated data |

**Postcondition:**  
Delete the booking


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>

##

<br>
<br>

### ID: SWAT-34013 - Title: Partial update: depositpaid field with valid data

**Priority:** P1

**Precondition:**  
Authorize as admin  
Create booking with valid data  

**Test data:**    
Content-Type: application/json  
Accept: application/json  
depositpaid - fasle  
 
**Request structure:**

Endpoint https://restful-booker.herokuapp.com/booking/id

Request Body
```json
{
   "depositpaid": true  // boolean
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
  "additionalneeds": "/* string */"
}
```

**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send PATCH request /booking/id with test data in request body  | Request is sent.  |
| 2  | Check code status  | HTTP Status 200 OK  |
| 3  | Check structure  of response body | Response body contains expected keys.  |
| 4  | Check value of keys | Value is changed to updated data |

**Postcondition:**  
Delete the booking


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>

##

<br>
<br>

### ID: SWAT-34014 - Title: Partial update: checkin field with valid data

**Priority:** P1

**Precondition:**  
Authorize as admin  
Create booking with valid data  

**Test data:**    
Content-Type: application/json  
Accept: application/json  
checkin - 2028-01-01  

 
**Request structure:**

Endpoint https://restful-booker.herokuapp.com/booking/id

Request Body
```json
{
  "bookingdates": {
    "checkin": "2026-06-20"  // date,  CCYY-MM-DD
  }
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
  "additionalneeds": "/* string */"
}
```

**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send PATCH request /booking/id with test data in request body  | Request is sent.  |
| 2  | Check code status  | HTTP Status 200 OK  |
| 3  | Check structure  of response body | Response body contains expected keys.  |
| 4  | Check value of keys | Value is changed to updated data |

**Postcondition:**  
Delete the booking


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>

##

<br>
<br>

### ID: SWAT-34015 - Title: Partial update: checkout field with valid data

**Priority:** P1

**Precondition:**  
Authorize as admin  
Create booking with valid data  

**Test data:**    
Content-Type: application/json  
Accept: application/json  
checkout - 2028-01-01  

 
**Request structure:**

Endpoint https://restful-booker.herokuapp.com/booking/id

Request Body
```json
{
 "bookingdates": {
 
    "checkout": "2026-06-25"  // date,  CCYY-MM-DD
  }
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
  "additionalneeds": "/* string */"
}
```

**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send PATCH request /booking/id with test data in request body  | Request is sent.  |
| 2  | Check code status  | HTTP Status 200 OK  |
| 3  | Check structure  of response body | Response body contains expected keys.  |
| 4  | Check value of keys | Value is changed to updated data |

**Postcondition:**  
Delete the booking


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>

##

<br>
<br>

### ID: SWAT-34016 - Title: Partial update booking with header Accept: application/xml

**Priority:** P2

**Precondition:**  
Authorize as admin   
Create booking with valid data  

**Test data:**    
Header Accept : "application/xml"

firstname - Name  

 
**Request structure:**

Endpoint https://restful-booker.herokuapp.com/booking/id

Request Body
```json
{
  "firstname": "/* string */"
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
| 1  | Send PATCH request  /booking/id with test data in request body  | Request is sent.  |
| 2  | Check code status  | HTTP Status 200 OK  |
| 3  | Check structure  of response body | Respons body is present in XML format. Response body contains expected keys.  |
| 4  | Check value of keys | Value is changed to updated data |

**Postcondition:**    
Delete the booking


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>

## Negative

<br>
<br>

### ID: SWAT-34017 - Title: Partial update non-existent booking

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
  "firstname": "/* string */"
}
```



**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send PATCH request  /booking/id with test data in request body  | Request is sent.  |
| 2  | Check code status  | HTTP Status 404 Not Found  |
| 3  | Check structure  of response body | Response body contains text `Not Found`  |

**Postcondition:**  



**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>

##

<br>
<br>

### ID: SWAT-34018 - Title: Partial update booking without header Content-Type

**Priority:** P3

**Precondition:**  
Authorize as admin   
Create booking with valid data  

**Test data:**    
Content-Type: (empty)   
firstname - Name  

**Request structure:**

Endpoint https://restful-booker.herokuapp.com/booking/id

Request Body
```json
{
  "firstname": "/* string */"
}
```


**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send PATCH request  /booking/id with test data in request body  | Request is sent.  |
| 2  | Check code status  | HTTP Status 400 Bad Request  |
| 3  | Check structure  of response body | Response body contains text `Bad Request`  |


**Postcondition:**  


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>

##

<br>
<br>

### ID: SWAT-34019 - Title: Partial update booking without header Accept

**Priority:** P3

**Precondition:**  
Authorize as admin   
Create booking with valid data  

**Test data:**    
Accept: (empty)   
firstname - Name  


**Request structure:**

Endpoint https://restful-booker.herokuapp.com/booking/id

Request Body
```json
{
  "firstname": "/* string */"
}
```

**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send PATCH request  /booking/id with test data in request body  | Request is sent.  |
| 2  | Check code status  | HTTP Status 400 Bad Request  |
| 3  | Check structure  of response body | Response body contains text `Bad Request`  |


**Postcondition:**  
Delete booking


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>

##

<br>
<br>

### ID: SWAT-34020 - Title: Partial update booking with invalid value of Content-Type header

**Priority:** P3

**Precondition:**  
Authorize as admin   
Create booking with valid data  

**Test data:**    
Content-Type : text/plain  
firstname - Name  


**Request structure:**

Endpoint https://restful-booker.herokuapp.com/booking/id

Request Body
```json
{
  "firstname": "/* string */"
}
```


**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send PATCH request  /booking/id with test data in request body  | Request is sent.  |
| 2  | Check code status  | HTTP Status 400 Bad Request  |
| 3  | Check structure  of response body | Response body contains text `Bad Request`  |


**Postcondition:**    
Delete booking  


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>

##

<br>
<br>

### ID: SWAT-34021 - Title: Partial update booking: firstname field validation

**Priority:** P2

**Precondition:**  
Authorize as admin   
Create booking with valid data  

**Test data:**    

firstname - ""  
firstname - 69  
firstname - null  
firstname - { object }  




**Request structure:**

Endpoint https://restful-booker.herokuapp.com/booking/id

Request Body
```json
{
  "firstname": "/* string */"
}
```


**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send PATCH request  /booking/id with  firstname = ""  | Request is sent.  |
| 2  | Check code status  | HTTP Status 422 Unprocessable Entity  |
| 3  | Send PATCH request  /booking/id with  firstname = 69  | Request is sent.  |
| 4  | Check code status  | HTTP Status 400 Bad Request  |
| 5  | Send PATCH request  /booking/id with  firstname = null  | Request is sent.  |
| 6  | Check code status  | HTTP Status 400 Bad Request  |
| 7  | Send PATCH request  /booking/id with  firstname = { object }  | Request is sent.  |
| 8  | Check code status  | HTTP Status 400 Bad Request  |



**Postcondition:**  
Delete booking


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>

##

<br>
<br>

### ID: SWAT-34022 - Title: Partial update booking: lastname field validation

**Priority:** P2

**Precondition:**  
Authorize as admin   
Create booking with valid data  

**Test data:**    

lastname  - ""  
lastname  - 69  
lastname  - null  
lastname - { object }  



**Request structure:**

Endpoint https://restful-booker.herokuapp.com/booking/id

Request Body
```json
{
 
  "lastname": "/* string */"
}
```


**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send PATCH request  /booking/id with  lastname  = ""  | Request is sent.  |
| 2  | Check code status  | HTTP Status 422 Unprocessable Entity  |
| 3  | Send PATCH request  /booking/id with  lastname  = 69  | Request is sent.  |
| 4  | Check code status  | HTTP Status 400 Bad Request  |
| 5  | Send PATCH request  /booking/id with  lastname  = null  | Request is sent.  |
| 6  | Check code status  | HTTP Status 400 Bad Request  |
| 7  | Send PATCH request  /booking/id with  lastname = { object }  | Request is sent.  |
| 8  | Check code status  | HTTP Status 400 Bad Request  |



**Postcondition:**  
Delete booking


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>

##

<br>
<br>

### ID: SWAT-34023 - Title: Partial update booking: totalprice field validation

**Priority:** P2

**Precondition:**  
Authorize as admin   
Create booking with valid data  

**Test data:**    

totalprice  - -1  
totalprice  - 0  
totalprice  - "qwerty"  
totalprice - { object }  



**Request structure:**

Endpoint https://restful-booker.herokuapp.com/booking/id

Request Body
```json
{
  "totalprice": 100  // number
}
```


**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send PATCH request  /booking/id with  totalprice  = 1  | Request is sent.  |
| 2  | Check code status  | HTTP Status 422 Unprocessable Entity  |
| 3  | Send PATCH request  /booking/id with  totalprice  = 0  | Request is sent.  |
| 4  | Check code status  | HTTP Status 422 Unprocessable Entity  |
| 5  | Send PATCH request  /booking/id with  totalprice  = "qwerty"  | Request is sent.  |
| 6  | Check code status  | HTTP Status 400 Bad Request  |
| 7  | Send PATCH request  /booking/id with  totalprice = { object }  | Request is sent.  |
| 8  | Check code status  | HTTP Status 400 Bad Request  |



**Postcondition:**  
Delete booking


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>

##

<br>
<br>

### ID: SWAT-34024 - Title: Partial update booking: depositpaid field validation

**Priority:** P2

**Precondition:**  
Authorize as admin   
Create booking with valid data  

**Test data:**    

depositpaid  - -1  
depositpaid  - 0  
depositpaid  - "0"  
depositpaid - null  
depositpaid - { object }  



**Request structure:**

Endpoint https://restful-booker.herokuapp.com/booking/id

Request Body
```json
{
  "depositpaid": true  // boolean
}
```


**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send PATCH request  /booking/id with  depositpaid  = -1  | Request is sent.  |
| 2  | Check code status  | HTTP Status 400 Bad Request  |
| 3  | Send PATCH request  /booking/id with  depositpaid  = 0  | Request is sent.  |
| 4  | Check code status  | HTTP Status 400 Bad Request  |
| 5  | Send PATCH request  /booking/id with  depositpaid  = "0"  | Request is sent.  |
| 6  | Check code status  | HTTP Status 400 Bad Request  |
| 7  | Send PATCH request  /booking/id with  depositpaid  = null  | Request is sent.  |
| 8  | Check code status  | HTTP Status 400 Bad Request  |
| 9  | Send PATCH request  /booking/id with  depositpaid = { object }  | Request is sent.  |
| 10 | Check code status  | HTTP Status 400 Bad Request  |


**Postcondition:**  
Delete booking


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>

##

<br>
<br>

### ID: SWAT-34025 - Title: Partial update booking: checkin field validation

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
checkin - { object }  


**Request structure:**

Endpoint https://restful-booker.herokuapp.com/booking/id

Request Body
```json
{
  "bookingdates": {
    "checkin": "2026-06-20"  // date,  CCYY-MM-DD
    }
}
```



**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send PATCH request  /booking/id with  checkin  = 1  | Request is sent.  |
| 2  | Check code status  | HTTP Status 400 Bad Request  |
| 3  | Send PATCH request  /booking/id with  checkin  = "qwerty"  | Request is sent.  |
| 4  | Check code status  | HTTP Status 400 Bad Request  |
| 5  | Send PATCH request  /booking/id with  checkin  = "2018"  | Request is sent.  |
| 6  | Check code status  | HTTP Status 422 Unprocessable Entity  |
| 7  | Send PATCH request  /booking/id with  checkin  = "2018-13-32"  | Request is sent.  |
| 8  | Check code status  | HTTP Status 422 Unprocessable Entity  |
| 9  | Send PATCH request  /booking/id with  checkin  = null  | Request is sent.  |
| 10  | Check code status  | HTTP Status 400 Bad Request  |
| 11  | Send PATCH request  /booking/id with  checkin = { object }  | Request is sent.  |
| 12 | Check code status  | HTTP Status 400 Bad Request  |

**Postcondition:**  
Delete booking


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>

##

<br>
<br>

### ID: SWAT-34026 - Title: Partial update booking: checkout field validation

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
checkout - { object }  


**Request structure:**

Endpoint https://restful-booker.herokuapp.com/booking/id

Request Body
```json
{
  "bookingdates": {
      "checkout": "2026-06-25"  // date,  CCYY-MM-DD
  }
}
```


**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send PATCH request  /booking/id with  checkout  = 1  | Request is sent.  |
| 2  | Check code status  | HTTP Status 400 Bad Request  |
| 3  | Send PATCH request  /booking/id with  checkout  = "qwerty"  | Request is sent.  |
| 4  | Check code status  | HTTP Status 400 Bad Request  |
| 5  | Send PATCH request  /booking/id with  checkout  = "2018"  | Request is sent.  |
| 6  | Check code status  | HTTP Status 422 Unprocessable Entity  |
| 7  | Send PATCH request  /booking/id with  checkout  = "2018-13-32"  | Request is sent.  |
| 8  | Check code status  | HTTP Status 422 Unprocessable Entity  |
| 9  | Send PATCH request  /booking/id with  checkout  = null  | Request is sent.  |
| 10  | Check code status  | HTTP Status 400 Bad Request  |
| 11  | Send PATCH request  /booking/id with  checkout = { object }  | Request is sent.  |
| 12 | Check code status  | HTTP Status 400 Bad Request  |

**Postcondition:**  
Delete booking

**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>

##

<br>
<br>

### ID: SWAT-34027 - Title: Partial update booking with empty request body

**Priority:** P1

**Precondition:**  
Authorize as admin   
Create booking with valid data  

**Test data:**    

**Request structure:**

Endpoint https://restful-booker.herokuapp.com/booking/id


**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send PATCH request /booking/id   | Request is sent.  |
| 2  | Check code status  | HTTP Status 400 Bad Request  |

**Postcondition:**  
Delete booking

**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

