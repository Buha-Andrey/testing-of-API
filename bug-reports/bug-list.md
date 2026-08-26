***Bug-reports***
```
BUG-001: POST /auth returns 200 OK for invalid credentials
BUG-002: POST /auth returns 200 OK for invalid data in request body
BUG-003: POST /auth returns 200 OK for missing Content-Type header
BUG-004: DELETE /booking/{id} returns 201 Created for successful deleting of the booking
BUG-005: Booking is absent from GET /booking response when query parameter `checkin` is equal to the request body parameter `checkin`  
BUG-006: API documentation has an incorrect description of the checkout parameter for GET /booking request
BUG-007: GET /booking/{id} returns 404 Not Found when Accept header is missing from the request
BUG-008: GET /booking/{id} returns 404 Not Found for non-numeric ID
BUG-009: POST /booking returns 200 OK when valid request is sent
BUG-010: POST /booking returns 500 Internal Server Error when Content-Type header is missing in the request
BUG-011: POST /booking returns 418 I'm a teapot when Accept header is missing in the request
BUG-012: POST /booking returns 500 Internal Server Error when the request is sent with invalid value of Content-Type header
BUG-013: 200 OK is returned on multiple endpoints when firstname/lastname properties are set to an empty string
BUG-014: 500 Internal Server Error is returned on multiple endpoints when firstname/lastname properties are set to a number
BUG-015: 500 Internal Server Error is returned on multiple endpoints when firstname/lastname properties are set to null 
BUG-016: 500 Internal Server Error is returned on multiple endpoints when firstname/lastname properties are set to an object 
BUG-017: 500 Internal Server Error is returned on multiple endpoints when firstname/lastname/totalprice/depositpaid/checkin/checkout properties are missing
BUG-018: 200 OK is returned on multiple endpoints when totalprice property is set to non-positive number
BUG-019: 200 OK is returned on multiple endpoints when totalprice property is set to a string 
BUG-020: 200 OK is returned on multiple endpoints when totalprice property is set to an object 
BUG-021: 200 OK is returned on multiple endpoints when depositpaid property is set to an object, string or non-zero number
BUG-022: 200 OK is returned on multiple endpoints when depositpaid property is set to zero 
BUG-023: 200 OK is returned on multiple endpoints when checkin/checkout properties are set to a number
BUG-024: 200 OK is returned on multiple endpoints when checkin/checkout properties are set to a string 
BUG-025: 200 OK is returned on multiple endpoints when checkin/checkout properties are set to an invalid date format 
BUG-026: 200 OK is returned on multiple endpoints when checkin/checkout properties are set to a year-only format
BUG-027: 200 OK is returned on multiple endpoints when checkin/checkout properties are set to an object
BUG-028: POST /booking returns 200 OK when checkin date is later than checkout date
BUG-029: POST /booking returns 500 Internal Server Error when request body is empty
BUG-030: 405 Method Not Allowed is returned on PUT/PATCH endpoints when booking ID does not exist
BUG-031: Decimal value of totalprice property is rounded to an integer on POST/PUT/PATCH endpoints
BUG-032: checkout value is lost after checkin update with PATCH /booking/{id}
BUG-033: PATCH /booking/{id} returns 200 OK when Content-Type header is missing in the request
BUG-034: PATCH /booking/{id} returns 500 Internal Server Error when Accept header is missing in the request
BUG-035: PATCH /booking/{id} returns 200 OK when the request is sent with invalid value of Content-Type header
BUG-036: PATCH /booking/{id} returns 200 OK when firstname/lastname properties are set to a number
BUG-037: PATCH /booking/{id} returns 405 Method Not Allowed when firstname/lastname properties are set to null
BUG-038: PATCH /booking/{id} returns 200 OK when firstname/lastname properties are set to an object
BUG-039: PATCH /booking/{id} returns 200 OK when depositpaid property is set to null
BUG-040: PATCH /booking/{id} returns 200 OK when checkin/checkout properties are set to null
BUG-041: PATCH /booking/{id} returns 200 OK when request body is empty
BUG-042: 405 Method Not Allowed is returned on PUT/PATCH/DELETE endpoints when booking ID is set to non-numeric value
```
