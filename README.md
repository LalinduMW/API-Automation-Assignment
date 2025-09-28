# API-Automation-Assignment

This project contains automated API test cases for the [JSONPlaceholder](https://jsonplaceholder.typicode.com/posts) fake REST API.  
The tests were created and executed using the Postman tool with support for schema validation, chained requests, data-driven testing, performance checks, and concurrency validation.  

---

## Tools and Technologies
- Tool: Postman  
- Assertions: Postman Tests (JavaScript)  
- Collection Runner: For batch execution and data-driven tests  
- Data Source: JSON (for data-driven cases)  

---

## Test Scenarios

### Test 1 — Get All Posts with Schema Validation
- Positive Case: Response should be an array.  
- Negative Case: Array is empty.  

### Test 2 — Data-Driven Get Single Post
- Positive Case: Check if the correct Id is returned.  
- Negative Case: Check if the correct title is returned.  

### Test 3 — Create Post (Chained Tests)
- Positive Case: Check if the post was created with the correct title and body.  
- Negative Case: Verify created postId.  

### Test 4 — Update Post with Partial Data (PATCH)
- Positive Case: Check if title updated got updated with the correct value.  
- Negative Case: Check if body updated got updated with the correct value.  

### Test 5 — Delete Post and Verify Non-Existence
- Positive Case: Verify Non-Existence.  
- Negative Case: Verify the deleted object contains the title.  

### Test 6 — Performance and Pagination Validation
- Performance: Ensure `GET /posts` response time is less than 500ms.  
- Pagination:  
  - Use `/posts?_page=1&_limit=10`.  
  - Verify exactly 10 posts are returned.  

### Test 7 — Concurrency and Data Consistency (Advanced)
- Fire multiple parallel POST requests with different payloads.  
- Verify all created posts return unique IDs.  

---

## Running the Tests

### Postman Collection Runner
1. Import the collection and environment into Postman.  
2. Open Collection Runner.  
3. Select the collection, environment, and data file (for data-driven tests).  
4. Run all tests (optionally in parallel).
