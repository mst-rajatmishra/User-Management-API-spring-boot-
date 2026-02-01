# User Management API

A simple Spring Boot REST API for managing users with CRUD operations.

## Features

- Create, Read, Update, and Delete (CRUD) operations for users
- RESTful API endpoints
- In-memory H2 database
- JPA/Hibernate for data persistence
- Lombok for reducing boilerplate code

## Technologies Used

- Java 17
- Spring Boot 3.2.2
- Spring Data JPA
- H2 Database
- Maven
- Lombok

## Prerequisites

- Java 17 or higher
- Maven 3.6 or higher

## Project Structure

```
src/
├── main/
│   ├── java/
│   │   └── com/example/usermanagement/
│   │       ├── UserManagementApplication.java
│   │       ├── controller/
│   │       │   └── UserController.java
│   │       ├── model/
│   │       │   └── User.java
│   │       ├── repository/
│   │       │   └── UserRepository.java
│   │       └── service/
│   │           └── UserService.java
│   └── resources/
│       └── application.properties
└── test/
```

## Getting Started

### Build the Project

```bash
mvn clean install
```

### Run the Application

```bash
mvn spring-boot:run
```

The application will start on `http://localhost:8080`.

## API Endpoints

### Get All Users
```
GET http://localhost:8080/api/users
```

### Get User by ID
```
GET http://localhost:8080/api/users/{id}
```

### Create a New User
```
POST http://localhost:8080/api/users
Content-Type: application/json

{
  "name": "John Doe",
  "email": "john.doe@example.com",
  "phone": "1234567890"
}
```

### Update a User
```
PUT http://localhost:8080/api/users/{id}
Content-Type: application/json

{
  "name": "Jane Doe",
  "email": "jane.doe@example.com",
  "phone": "0987654321"
}
```

### Delete a User
```
DELETE http://localhost:8080/api/users/{id}
```

## H2 Database Console

Access the H2 database console at: `http://localhost:8080/h2-console`

- JDBC URL: `jdbc:h2:mem:testdb`
- Username: `sa`
- Password: (leave empty)

## Testing the API

You can test the API using:
- cURL
- Postman
- Any REST client

Example with cURL:
```bash
# Create a user
curl -X POST http://localhost:8080/api/users \
  -H "Content-Type: application/json" \
  -d '{"name":"John Doe","email":"john@example.com","phone":"1234567890"}'

# Get all users
curl http://localhost:8080/api/users
```
