# Expense Tracker API

A RESTful API for managing personal expenses built with Spring Boot.

## Tech Stack

- Java 17
- Spring Boot 3.2.0
- Spring Security with JWT Authentication
- Spring Data JPA
- H2 Database (file-based persistence)
- Maven
- OpenAPI/Swagger UI (SpringDoc)
- Bean Validation

## Features

- User registration and authentication with JWT
- CRUD operations for expense/income transactions
- Transaction filtering by date range
- Transaction types: INCOME and EXPENSE
- Category-based transaction organization
- Secure endpoints with Spring Security
- API documentation with Swagger UI
- CORS enabled for cross-origin requests

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
  - Body: `{ "username": "string", "email": "string", "password": "string" }`
- `POST /api/auth/login` - Login and receive JWT token
  - Body: `{ "username": "string", "password": "string" }`

### Transactions

- `GET /api/transactions` - Get all user transactions
- `GET /api/transactions/{id}` - Get transaction by ID
- `POST /api/transactions` - Create new transaction
  - Body: `{ "description": "string", "amount": number, "type": "INCOME|EXPENSE", "date": "YYYY-MM-DD" }`
- `PUT /api/transactions/{id}` - Update transaction
- `DELETE /api/transactions/{id}` - Delete transaction
- `GET /api/transactions/filter?startDate=YYYY-MM-DD&endDate=YYYY-MM-DD` - Filter transactions by date range

## Database

H2 Console: `http://localhost:8080/h2-console`

- JDBC URL: `jdbc:h2:file:./data/expensedb`
- Username: `sa`
- Password: (empty)

Data is persisted to `./data/expensedb` file.

## Configuration

Edit `src/main/resources/application.properties` to customize:

- Server port (default: 8080)
- Database settings
- JWT secret and expiration (default: 24 hours)
- H2 console access

## Project Structure

```
src/main/java/com/expense/tracker/
├── config/          # Security configuration
├── controller/      # REST controllers
├── dto/             # Data transfer objects
├── entity/          # JPA entities
├── repository/      # Data repositories
├── security/        # JWT authentication
└── service/         # Business logic
```
