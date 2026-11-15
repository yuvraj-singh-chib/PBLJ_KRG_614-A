# Student Management System (Spring Boot REST API)

A REST API to manage student records, built with Spring Boot 3, Spring Data JPA and MySQL.

## Tech stack
- Java 17+
- Spring Boot 3.3.5 (Web, Data JPA, Validation)
- MySQL 8
- Maven

## Project structure
```
src/main/java/com/example/studentmanagement
├── StudentManagementApplication.java
├── controller/StudentController.java
├── entity/Student.java
├── exception/  (StudentNotFoundException, DuplicateEmailException, ErrorResponse, GlobalExceptionHandler)
├── repository/StudentRepository.java
└── service/StudentService.java
src/main/resources/application.properties
postman_collection.json
```

## Setup
1. Install Java 17+ and Maven, and make sure MySQL is running.
2. Open `src/main/resources/application.properties` and set your MySQL `username` and `password`.
   The database `student_db` and the `students` table are created automatically on first run.
3. Run:
   ```
   mvn spring-boot:run
   ```
   The API starts at `http://localhost:8080`.

## Endpoints
| Method | Endpoint | Description | Success | Errors |
|--------|----------|-------------|---------|--------|
| POST | /api/students | Add a new student | 201 Created | 400 validation, 409 duplicate email |
| GET | /api/students | Get all students | 200 OK | - |
| GET | /api/students/{id} | Get student by ID | 200 OK | 404 not found |
| PUT | /api/students/{id} | Update student | 200 OK | 400, 404, 409 |
| DELETE | /api/students/{id} | Delete student | 200 OK | 404 not found |
| GET | /api/students/course/{course} | Get students by course | 200 OK (empty list if none) | - |

### Sample request body
```json
{
  "name": "Rahul Sharma",
  "email": "rahul.sharma@example.com",
  "course": "Computer Science",
  "age": 21
}
```

### Sample error response (404)
```json
{
  "timestamp": "2026-11-14T23:30:00",
  "status": 404,
  "error": "Not Found",
  "message": "Student not found with id: 999",
  "fieldErrors": null
}
```

## Testing with Postman
Import `postman_collection.json` (Postman -> Import) and run the requests in order.
The collection covers all six endpoints plus a 404 and a 400 case. Take a screenshot of each request/response
for your submission.
