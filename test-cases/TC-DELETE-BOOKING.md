## Positive

### ID: SWAT-34030 - Title: Delete existing booking

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
| 1  | Send DELETE request  /booking/id  | Request is sent.  |
| 2  | Check code status  | HTTP Status 204 No Content  |
| 3  | Check structure  of response body | Response body contains text `No Content`  |



**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>

## Negative

<br>
<br>

### ID: SWAT-34031 - Title: Delete non-existent booking

**Priority:** P2

**Precondition:**  
Authorize as admin  

**Test data:**    
ID = 9999
 
**Request structure:**

Endpoint https://restful-booker.herokuapp.com/booking/id


**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send DELETE request  /booking/id  | Request is sent.  |
| 2  | Check code status  | HTTP Status 404 Not Found |
| 3  | Check structure  of response body | Error message is returned. |



**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii

<br>

## 

<br>
<br>

### ID: SWAT-34032 - Title: Delete booking: ID parameter validation

**Priority:** P2

**Precondition:**  
Authorize as admin  

**Test data:**    

**Request structure:**

Endpoint https://restful-booker.herokuapp.com/booking/id


**Steps:**
|   #   | Step | Expected result |
|:-----------|-----------|-----------|
| 1  | Send DELETE request /booking/0  | Request is sent.  |
| 2  | Check code status  | HTTP Status 404 Not Found  |
| 3  | Check response body  | Error message is returned.  |
| 4  | Send DELETE request /booking/-10  | Request is sent.  |
| 5  | Check code status  | HTTP Status 404 Not Found |
| 6  | Check response body  | Error message is returned.  |
| 7  | Send DELETE request /booking/qwerty  | Request is sent.  |
| 8  | Check code status  | HTTP Status 400 Bad Request  |
| 9  | Check response body  | Error message is returned.  |


**Tags:** automated

**Additional info:** https://restful-booker.herokuapp.com/apidoc/index.html

**Created by:** Buha Andrii
