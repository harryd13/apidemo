# Spring Boot REST API Demo

## Overview
This is a simple **REST API** built with **Spring Boot**, using an in-memory **H2 database**. It provides CRUD operations for a `User` entity.

## Features
- RESTful API with standard HTTP methods
- Uses **Spring Data JPA** for database interactions
- In-memory **H2 database** (easily switchable to MySQL/PostgreSQL)
- Handles basic CRUD operations

## Tech Stack
- **Spring Boot** (Backend Framework)
- **Spring Web** (REST API)
- **Spring Data JPA** (ORM & Database Interaction)
- **H2 Database** (In-Memory Database for Testing)
- **Maven** (Build Tool)

## Getting Started
### 1. Clone the Repository
```bash
git clone https://github.com/harryd13/apidemo.git
cd springboot-rest-api-demo
```

### 2. Build and Run the Application
```bash
mvn spring-boot:run
```
This will start the server on `http://localhost:8080`.

### 3. API Endpoints

| Method | Endpoint          | Description           |
|--------|------------------|----------------------|
| GET    | `/api/users`     | Get all users       |
| GET    | `/api/users/{id}` | Get user by ID      |
| POST   | `/api/users`     | Create a new user   |
| PUT    | `/api/users/{id}` | Update user by ID   |
| DELETE | `/api/users/{id}` | Delete user by ID   |

### 4. Example API Requests
#### **GET All Users**
```bash
curl -X GET http://localhost:8080/api/users
```
#### **POST Create User**
```bash
curl -X POST http://localhost:8080/api/users \
     -H "Content-Type: application/json" \
     -d '{"id": 1, "name": "John Doe", "email": "john@example.com"}'
```
#### **GET User by ID**
```bash
curl -X GET http://localhost:8080/api/users/1
```
#### **PUT Update User**
```bash
curl -X PUT http://localhost:8080/api/users/1 \
     -H "Content-Type: application/json" \
     -d '{"name": "John Updated", "email": "john.updated@example.com"}'
```
#### **DELETE User by ID**
```bash
curl -X DELETE http://localhost:8080/api/users/1
```

### 5. H2 Database Console (For Testing)
Once the app is running, open `http://localhost:8080/h2-console` in your browser. Use the following credentials:
- **JDBC URL**: `jdbc:h2:mem:testdb`
- **Username**: `sa`
- **Password**: `password`

### 6. Switching to MySQL (Optional)
To use MySQL instead of H2, update `src/main/resources/application.properties`:
```properties
spring.datasource.url=jdbc:mysql://localhost:3306/your_db
spring.datasource.username=root
spring.datasource.password=your_password
spring.jpa.hibernate.ddl-auto=update
spring.jpa.database-platform=org.hibernate.dialect.MySQL8Dialect
```

### License
This project is open-source and available for use under the **MIT License**.

---
Feel free to modify and expand this API as needed!

