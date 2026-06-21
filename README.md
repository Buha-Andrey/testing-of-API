# testing-of-restful-booker
https://restful-booker.herokuapp.com/apidoc/index.html

Checklist of TC-AUTH POST /auth  
1. Authentication with valid credentials.
2. POST /auth generates unique token on each request  
3. Authentication fails with incorrect password  
4. Authentication fails with incorrect username  
5. Authentication with empty username  
6. Authentication with empty password  
7. Authentication without header Content-Type  
8. Authentication with invalid value of Content-Type header  

Checklist of TC-GET-BOOKING-IDS GET /booking
1. Get list of booking ids
2. Filter booking by firstname, lastname, checkin, checkout
3. Boundary value analysis of checkin date
4. Boundary value analysis of checkout date


Checklist of TC-UPDATE-BOOKING PUT /booking/:id
1. Update booking: all fields with valid data 
2. Update booking with header Accept: application/xml
3. Update non-existent booking
4. Update booking without header Content-Type
5. Update booking without header Accept 
6. Update booking with invalid value of Content-Type header
7. Update booking: firstname field validation
8. Update booking: lastname field validation
9. Update booking: totalprice field validation
10. Update booking: depositpaid field validation
11. Update booking: checkin field validation
12. Update booking: checkout field validation
13. Update booking: additionalneeds field validation

|  # | description  | 
|:-----------|-----------|
|1.| Update all fields with valid data |
|2.| Update booking with Accept header = application/xml|
|3.| Update booking with non-existent ID |
|4.| Update booking with no Content-Type header |
|5.| Update booking with invalid value of Content-Type header |
|6.| Update booking with invalid value of firstname |
|7.| Update booking with invalid value of lastname |
|8.| Update booking with invalid value of totalprice |
|9.| Update booking with invalid value of checkout |
|10.| Update booking with invalid value of checkin |
|11.| Update booking with invalid value of additionalneeds |
|12.| Update booking using invalid method |








Checklist of TC-PARTIAL-UPDATE-BOOKING PATCH /booking/:id
1. update firstname with valid data using auth through Cookie
2. update lastname with valid data using Basic authorization
3. update totalprice with valid data
4. update depositpaid with valid data
5. update checkin with valid data
6. update checkout with valid data
7. update additional needs with valid data
