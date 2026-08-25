# Test Plan
 
**Project:** Restful-Booker API - QA Testing    
**Prepared by:** Buha Andrii    
**Related documents:** Test Cases, Traceability Matrix, Bug Reports, Test Summary Report    

---
## 1. Context of testing

**Test scope**    

API: Restful-Booker API (https://restful-booker.herokuapp.com)    
API doc: https://restful-booker.herokuapp.com/apidoc/index.html

The following endpoints are covered:
- Auth
  - POST /auth
- Booking
  - POST /booking
  - GET /booking
  - GET /booking/{id}
  - PUT /booking/{id}
  - PATCH /booking/{id}
  - DELETE /booking/{id}

<br>

**Out of Scope**     
- Performance / load testing API
- UI testing (API-only project, no UI)
- Security testing

<br>

**Test objectives** 
- Verify that Booking CRUD endpoints work correctly according to the test basis.
- Identify and document any differences between the actual API behavior and the API documentation.
- Identify and report defects 
- Cover all Booking endpoints with both positive and negative test-cases.

<br>

**Test basis**
- Restful-Booker API documentation (https://restful-booker.herokuapp.com/apidoc/index.html)
- Tester's domain knowledge and prior experience with testing

---
## 2. Assumptions & Constraints
**Assumptions:**
The Restful-Booker API will remain available and free. 

**Constraints:**
Test data created by other users of the same public API may interfere with test results.

---
## 3. The Team
| Role | Who | Responsibility |
|---|---|---|
| QA | Andrii Buha | Test planning, test execution, writing auto-tests, bug reporting |

**Training needs:**     
- JavaScript - required to write test scripts inside Postman
- Chai - assertion library, used within Postman

---
## 4. Risk register
| Description | Probability | Impact | Mitigation |
|---|---|---|---|
|API resets itself every 10 minutes back to that default state. | High | High | Need to create test data at the start every test run. |
|Other user can delete/modify data, affecting test result | Low  | Medium  | Create only unique test data and test your own data |

---
## 5. Test approach
### 5.1 Test levels
System testing - the API will be tested as a black box, without access to internal implementation.

### 5.2 Test types 
- Functional testing (API testing) - each endpoint will be tested to verify that it behaves according to the test basis.
- Documentation testing - the API doc will be reviewed for clarity and cross-checked against actual API behavior to identify defects or missing information.

### 5.3 Test techniques
The following techniques will be used to design test cases:
- Equivalence partitioning and boundary value analysis - for validating checkin and checkout parameters.
- Error guessing - testing based on the tester's knowledge of common API issues.
- Checklist-based testing - for  covering each endpoint with set of positive/negative checks.

### 5.4 Test environment
Only one environment is available: prod - https://restful-booker.herokuapp.com
Note: The environment resets to default state every 10 minutes.

### 5.5 Testing tools
Postman - creation/sending HTTP requests, building test collection, writing test scripts    
GitHub - storage for test cases, bug reports, test plan and test summary report

### 5.6 Browser / OS
Chrome v. 151
Windows 11 v.25H2
Linux 

### 5.7 Test artefacts 
- Checklist
- Test cases 
- Bug reports
- Test plan
- Test summary report

### 5.8 Entry criteria / Exit criteria
Entry criteria:
- Required training completed
- API is accessible
- API documentation is available

Exit criteria:
- Every endpoint is covered with test-case
- Collection run is built
- All identified defects are documented as bug reports

### 5.9 Metrics to be collected
- Test coverage: % of endpoints with at least one test case (based on the traceability matrix)
- Defect density per endpoint: number of defects found, grouped by endpoint

### 5.10 Test data requirements
Unique test data will be generated for each test case:
```
  "firstname": "RestfulBooker",
  "lastname": "Test",
```
Also created bookings during test execution have to be deleted after test case.
