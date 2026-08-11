# testing-of-restful-booker
https://restful-booker.herokuapp.com/apidoc/index.html

<br>

***Checklist of TC-AUTH***  
**Authentication (POST /auth)**

Positive
1. Authentication with valid credentials.
2. POST /auth generates unique token on each request

Negative
1. Authentication fails with incorrect password  
2. Authentication fails with incorrect username  
3. Authentication with empty username  
4. Authentication with empty password  
5. Authentication without header Content-Type  

***Authorization (Token Usage)***

Positive
1. PUT with valid token
2. PATCH with valid token
3. DELETE with valid token

Negative
1. PUT without token
2. PATCH without token
3. DELETE without token
4. PUT with invalid token
5. PATCH with invalid token
6. DELETE with invalid token
 

<br>

**Checklist of TC-GET-BOOKING-IDS GET /booking**  

Positive
1. Get list of booking ids
2. Filter booking by firstname, lastname, checkin, checkout
3. Boundary value analysis of checkin date
4. Boundary value analysis of checkout date

<br>

**Checklist of TC-GET-BOOKING GET /booking/id**

Positive
1. Get booking with existing valid ID
2. Get booking with existing valid ID in xml format

Negative
1. Get booking without header Accept
2. Get booking with non-existent valid ID 
3. Get booking: ID parameter validation 

<br>

**Checklist of TC-CREATE-BOOKING POST /booking**

Positive
1. Create booking: all fields with valid data
2. POST /booking creates unique booking on each request
3. Create booking with header Accept: application/xml

Negative
1. Create booking without header Content-Type
2. Create booking without header Accept 
3. Create booking with invalid value of Content-Type header
4. Create booking: firstname field validation
5. Create booking: lastname field validation
6. Create booking: totalprice field validation
7. Create booking: depositpaid field validation
8. Create booking: checkin field validation
9. Create booking: checkout field validation
10. Create booking with checkin date that is later than checkout date
11. Create booking with empty request body

<br>

**Checklist of TC-UPDATE-BOOKING PUT /booking/:id**

Positive
1. Update booking: all fields with valid data 
2. Update booking with header Accept: application/xml

Negative
1. Update non-existent booking
2. Update booking without header Content-Type
3. Update booking without header Accept 
4. Update booking with invalid value of Content-Type header
5. Update booking: firstname field validation
6. Update booking: lastname field validation
7. Update booking: totalprice field validation
8. Update booking: depositpaid field validation
9. Update booking: checkin field validation
10. Update booking: checkout field validation
11. Update booking: additionalneeds field validation
12. Update booking with empty request body !!!!!!!!

<br>

**Checklist of TC-PARTIAL-UPDATE-BOOKING PATCH /booking/:id** 

Positive
1. Partial update: firstname field with valid data 
2. Partial update: lastname field with valid data 
3. Partial update: totalprice field with valid data
4. Partial update: depositpaid field with valid data
5. Partial update: checkin field with valid data
6. Partial update: checkout field with valid data
7. Partial update: additional needs field with valid data
8. Partial update booking with header Accept: application/xml

Negative
1. Partial update non-existent booking
2. Partial update booking without header Content-Type
3. Partial update booking without header Accept 
4. Partial update booking with invalid value of Content-Type header
5. Partial update booking: firstname field validation
6. Partial update booking: lastname field validation
7. Partial update booking: totalprice field validation
8. Partial update booking: depositpaid field validation
9. Partial update booking: checkin field validation
10. Partial update booking: checkout field validation
11. Partial update booking: additionalneeds field validation
12. Partial update booking with empty request body

<br>

**Checklist of TC-DELETE-BOOKING DELETE /booking/:id** 

Positive
1. Delete existing booking

Negative
1. Delete non-existent booking
2. Delete booking: ID parameter validation 



***Bug-reports***
```
BUG-001: POST /auth endpoint returns status code 200 OK instead of 401 Unauthorized for invalid credentials
BUG-002: POST /auth endpoint returns status code 200 OK instead of 400 Bad Request for invalid request body
BUG-003: POST /auth endpoint returns status code 200 OK instead of 400 Bad Request for missing Content-Type header
BUG-004: DELETE /booking/{id} endpoint returns status code 201 Created instead of 204 No Content for successful deleting of the booking
BUG-005: Booking is missing from GET /booking response when its checkin date matches the requested checkin filter
BUG-006: API documentation has an incorrect description of the checkout parameter for GET /booking request
BUG-007: GET /booking/{id} endpoint returns 404 Not Found when Accept header is missing from the request
BUG-008: GET /booking/{id} returns 404 Not Found instead of 400 Bad Request for non-numeric ID
BUG-009: POST /booking returns 200 OK instead of 201 Created when valid request is sent
BUG-010: POST /booking returns 500 Internal Server Error instead of 400 Bad Request when the request without header Content-Type is sent
BUG-011: POST /booking returns 418 I'm a teapot instead of 400 Bad Request when the request without header Accept is sent
BUG-012: POST /booking returns 500 Internal Server Error instead of 400 Bad Request when the request is sent with invalid value of Content-Type header
BUG-013: Sending request with empty string firstname/lastname returns 200 Ok instead of 422 Unprocessable Entity
BUG-014: Sending request with numeric firstname/lastname returns 500 Internal Server Error instead of 400 Bad Request
BUG-015: Sending request with null value of firstname/lastname returns 500 Internal Server Error instead of 400 Bad Request
BUG-016: Sending request with object value of firstname/lastname returns 500 Internal Server Error instead of 400 Bad Request
BUG-017: Sending request without firstname/lastname/totalprice/depositpaid/checkin/checkout fields returns 500 Internal Server Error instead of 400 Bad Request
BUG-018: Sending request with non-positive numeric value of totalprice returns 200 OK instead of 422 Unprocessable Entity
BUG-019: Sending request with string value of totalprice returns 200 OK instead of 400 Bad Request
BUG-020: Sending request with object value of totalprice returns 200 OK instead of 400 Bad Request
BUG-021: Sending request with object value, string value or not-zero number of depositpaid returns 200 OK instead of 400 Bad Request
BUG-022: Sending request with zero number of depositpaid returns 200 OK instead of 400 Bad Request
BUG-023: Sending request with number value of checkin/checkout returns 200 Internal Server Error instead of 400 Bad Request
```





Bugs:
SWAT-33951 - Filter booking by firstname, lastname, checkin, checkout - 
