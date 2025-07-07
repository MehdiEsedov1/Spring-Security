# Spring Security Example Project

This is a Java & Spring Boot-based project demonstrating modern authentication and authorization mechanisms using **Spring Security**, **JWT (JSON Web Tokens)**, and **role-based access control**.

## 🔐 Features

- Secure user authentication with JWT
- Role-based access control (e.g. USER, ADMIN)
- Token generation and validation
- Custom login and registration endpoints
- Stateless session management
- Password hashing with BCrypt
- Global exception handling for authentication errors

## 📦 Tech Stack

- Java 17
- Spring Boot
- Spring Security
- Spring Web
- Spring Data JPA
- JWT (jjwt)
- PostgreSQL / H2 (optional)
- Lombok

## 🚀 Endpoints

| Method | Endpoint            | Description              | Access        |
|--------|---------------------|--------------------------|---------------|
| POST   | `/api/auth/register` | User registration         | Public        |
| POST   | `/api/auth/login`    | User login & JWT issuing  | Public        |
| GET    | `/api/user/data`     | Access user data          | ROLE_USER     |
| GET    | `/api/admin/data`    | Access admin data         | ROLE_ADMIN    |

## 🔧 Getting Started

### Prerequisites

- Java 17+
- Maven or Gradle
- PostgreSQL (or H2 for testing)

### Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/MehdiEsedov1/Spring-Security.git
   cd Spring-Security
Configure your database in application.properties:

properties
Copy
Edit
spring.datasource.url=jdbc:postgresql://localhost:5432/spring_security_db
spring.datasource.username=your_username
spring.datasource.password=your_password
Run the application:

bash
Copy
Edit
./mvnw spring-boot:run
🛡️ Security Architecture
JWT is used for stateless authentication.

Access tokens are returned after successful login and must be sent in Authorization headers (Bearer <token>).

Each request is filtered and validated by custom JWT filters.

Authorities (roles) are extracted from token and used to enforce access.

📁 Project Structure

src/

├── config/             # Security configuration

├── controller/         # REST endpoints

├── dto/                # Request/Response DTOs

├── entity/             # JPA Entities

├── exception/          # Custom exception handlers

├── repository/         # JPA Repositories

├── security/           # JWT & authentication logic

├── service/            # Business logic

└── util/               # Utility classes

✅ Example Credentials

    {

    "username": "user1",

    "password": "password"

    }

📜 License
This project is open-source and free to use for educational or commercial purposes.