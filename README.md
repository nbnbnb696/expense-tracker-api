# Expense Tracker API

A RESTful API for managing personal expenses built with Spring Boot.

## Tech Stack

- Java 17
- Spring Boot 3.2.0
- Spring Security with JWT Authentication
- Spring Data JPA
- H2 Database
- Maven
- OpenAPI/Swagger UI

## Features

- User registration and authentication with JWT
- Create, read, update, and delete expense transactions
- Secure endpoints with Spring Security
- API documentation with Swagger UI
- H2 in-memory database with file persistence

## Prerequisites

- Java 17 or higher
- Maven 3.6+

## Getting Started

### Build the project

```bash
mvn clean install
```

### Run the application

```bash
mvn spring-boot:run
```

The API will start on `http://localhost:8080`

## API Documentation

Access Swagger UI at: `http://localhost:8080/swagger-ui.html`

## API Endpoints

### Authentication

- `POST /api/auth/register` - Register a new user
- `POST /api/auth/login` - Login and receive JWT token

### Transactions

- `GET /api/transactions` - Get all transactions (authenticated)
- `GET /api/transactions/{id}` - Get transaction by ID (authenticated)
- `POST /api/transactions` - Create new transaction (authenticated)
- `PUT /api/transactions/{id}` - Update transaction (authenticated)
- `DELETE /api/transactions/{id}` - Delete transaction (authenticated)

## Database

H2 Console: `http://localhost:8080/h2-console`

- JDBC URL: `jdbc:h2:file:./data/expensedb`
- Username: `sa`
- Password: (empty)

## Configuration

Edit `src/main/resources/application.properties` to customize:

- Server port
- Database settings
- JWT secret and expiration
