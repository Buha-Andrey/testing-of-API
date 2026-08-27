# Testing of CRUD Web API - QA Portfolio Project

**QA Engineer:** Buha Andrii

![Postman](https://img.shields.io/badge/Postman-FF6C37?style=for-the-badge&logo=postman&logoColor=white) ![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black) ![Quality Assurance](https://img.shields.io/badge/Quality%20Assurance-4B5563?style=for-the-badge)

This QA project demonstrates testing of the [Restful-Booker API](https://restful-booker.herokuapp.com/), showcasing API test automation skills and STLC process - from test planning to test reporting.

## What's here
| Artifact | Link |
|---|---|
| Test Plan | [`test-documentation/test-plan.md`](./test-documentation/test-plan.md) |
| Test Cases (76 total) | [`test-cases/`](./test-cases/) |
| Postman Collection | [`postman/collection/`](./postman/collection/) |
| HTML Run Report | [`postman/collection/report.html`](https://buha-andrey.github.io/testing-of-API/postman/report.html) |
| Bug Reports (42 found) | [`bug-reports/`](./bug-reports/) |
| Traceability Matrix | [`traceability-matrix/Traceability Matrix.csv`](https://docs.google.com/spreadsheets/d/111-6AXOlewD8npjZgfV-zUuCyTkDSOxg4d8EjTl8KXs/edit?usp=sharing) |
| Test Summary Report | [`test-documentation/test-summary-report.md`](./test-documentation/test-summary-report.md) |

## End-to-End Example

Tracing a single test case - from written test case, through request in Postman collection, to a discovered defect:

1. **Test Case**  [`SWAT-33951 - Filter booking by firstname, lastname, checkin, checkout`](https://github.com/Buha-Andrey/testing-of-API/blob/main/test-cases/TC-GET-BOOKING-IDS.md#id-swat-33951---title-filter-booking-by-firstname-lastname-checkin-checkout)
2. **Request in Postman collection**    
**Pre-request script:**    
Precondition: The booking is created using POST /booking.     
**Request:**    
GET /booking is sent with test data: query params and headers.     
**Post-request script:**    
Assertions to check response    
Postcondition:  Created booking is deleted and data is unset.    

4. **Bug Found**    
   According to the documentation GET /booking request have to return booking that has a checkin date equal to the set checkin date
5. **Bug Report**  [`BUG-005: Booking is absent from GET /booking response when query parameter checkin is equal to the request body parameter checkin`](https://github.com/Buha-Andrey/testing-of-API/blob/main/bug-reports/BUG-005.md)
