# Test Summary Report
 
**Project:** Restful-Booker API — QA Testing    
**Test basis:** https://restful-booker.herokuapp.com/apidoc/index.html    
**Prepared by:** Buha Andrii    
**Related documents:** Test Plan, Test Cases, Traceability Matrix, Bug Reports    
 
---
## 1. Test Scope
 
The following endpoints are covered:
 
- **Auth**
  - `POST /auth`
- **Booking**
  - `POST /booking`
  - `GET /booking`
  - `GET /booking/{id}`
  - `PUT /booking/{id}`
  - `PATCH /booking/{id}`
  - `DELETE /booking/{id}`

**Out of scope:** `GET /ping`, load/performance testing, security testing 

### Test Objectives
- Verified that Booking CRUD endpoints work correctly according to the test basis.
- Identified and documented any differences between the actual API behavior and the API documentation.
- Identified and reported defects 
- Covered all Booking endpoints with both positive and negative test-cases.'

---

## 2. Test Execution Summary
 
| Metric            | Result |
|-------------------|-------:|
| Total test cases  |     76 |
| Executed          |     76 |
| Passed            |     24 |
| Failed            |     52 |
| Pass rate         | 31.58% |
 
**Coverage:** All 7 endpoints in scope are covered by both positive and negative test cases; full mapping is available in the Traceability Matrix.
**Automation scripts:** 76 of 76 test cases are automated (100%), implemented as a Postman collection.

### Analysis
 
The pass rate of 31.58% is notably low: Restful-Booker is a public training API. Developer claims that API has "a bunch of bugs for you to explore."

## 3. Defect Summary
 
| Priority | Total |
|----------|------:|
| P0       |     0 |
| P1       |    20 |
| P2       |    11 |
| P3       |    11 |
| **Total**|   **42** |

### Notable Defects
 
| ID | Priority | Summary |
|----|----------|---------|
| BUG-005 | P1 | According to the documentation GET /booking request have to return booking that has a checkin date equal to the set checkin date |
| BUG-013 | P1 | Request with an empty string as the firstname/lastname value returns status code 200 Ok instead of 422 Unprocessable Entity.  |
| BUG-032 | P1 | checkout value is lost after checkin update with PATCH /booking/{id} |
 
