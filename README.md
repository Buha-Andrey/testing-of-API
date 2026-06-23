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

Checklist of TC-GET-BOOKING GET /booking/id
1. Get booking with existing valid ID
2. Get booking with existing valid ID in xml format
3. Get booking without header Accept
4. Get booking with non-existent valid ID 
5. Get booking: ID parameter validation 

Checklist of TC-CREATE-BOOKING POST /booking
1. Create booking: all fields with valid data
2. POST /booking creates unique booking on each request
3. Create booking with header Accept: application/xml
4. Create booking without header Content-Type
5. Create booking without header Accept 
6. Create booking with invalid value of Content-Type header
7. Create booking: firstname field validation
8. Create booking: lastname field validation
9. Create booking: totalprice field validation
10. Create booking: depositpaid field validation
11. Create booking: checkin field validation
12. Create booking: checkout field validation
13. Create booking with checkin date that is later than checkout date
14. Create booking with empty request body

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
14. Update booking with empty request body !!!!!!!!

Checklist of TC-PARTIAL-UPDATE-BOOKING PATCH /booking/:id !!!!!!!!
1. Partial update firstname with valid data 
2. Partial update lastname with valid data 
3. Partial update totalprice with valid data
4. Partial update depositpaid with valid data
5. Partial update checkin with valid data
6. Partial update checkout with valid data
7. Partial update additional needs with valid data
8. Partial update booking with header Accept: application/xml
9. Partial update non-existent booking
10. Partial update booking without header Content-Type
11. Partial update booking without header Accept 
12. Partial update booking with invalid value of Content-Type header
13. Partial update booking: firstname field validation
14. Partial update booking: lastname field validation
15. Partial update booking: totalprice field validation
16. Partial update booking: depositpaid field validation
17. Partial update booking: checkin field validation
18. Partial update booking: checkout field validation
19. Partial update booking: additionalneeds field validation
20. Partial update booking with empty request body

Checklist of TC-DELETE-BOOKING DELETE /booking/:id !!!!!!
1. Delete existing booking
2. Delete non-existent booking
3. Delete booking: ID parameter validation 
