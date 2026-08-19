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

<br>

## 2. Assumptions & Constraints
**Assumptions:**
The Restful-Booker API will remain available and free. 

**Constraints:**
Test data created by other users of the same public API may interfere with test results.


## 3. The Team
| Role | Who | Responsibility |
|---|---|---|
| QA | Andrii Buha | Test planning, test execution, writing auto-tests, bug reporting |

**Training needs:**     
- JavaScript - required to write test scripts inside Postman
- Chai - assertion library, used within Postman


## 4. Risk register
| Description | Probability | Impact | Mitigation |
|---|---|---|---|
|API resets itself every 10 minutes back to that default state. | High | High | Need to create test data at the start every test run. |
|Other user can delete/modify data, affecting test result | Low  | Medium  | Create only unique test data and test your own data |


## 5. Test approach
### 5.1 Test levels
- Unit testing 
- Integration testing 
- System testing 
- Acceptance testing

### 5.2 Test types 
- Functional testing
- Security testing (базові перевірки, якщо є auth/платежі)

### 5.3 Test techniques (Техніки)

### 5.4 Test environment

### 5.5 Testing tools

### 5.6 Browser / OS

### 5.7 Test artefacts 

### 5.8 Entry criteria / Exit criteria

### 5.9 Independence of testing

### 5.10 Metrics to be collected

### 5.11 Test data requirements
