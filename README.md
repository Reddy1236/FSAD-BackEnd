# Student Peer Review Backend

Backend API for the Student Peer Review and Collaboration Platform, built with Spring Boot.

## Tech Stack
- Java 21
- Spring Boot 3
- Spring Web
- Spring Data JPA
- MySQL for local development
- Optional PostgreSQL-style environment variables for deployment

## Features
- Authentication endpoints
- Project management APIs
- Peer review and reply APIs
- Reviewer assignment flows
- Teacher decision workflows
- Activity and notification data handling

## Prerequisites
- Java 21
- Maven 3.9 or later
- MySQL 8 or later

## Database Setup

Run the SQL script in MySQL Workbench or the MySQL CLI:

```text
database/mysql-workbench-setup.sql
```

## Configuration

Update environment variables or edit `src/main/resources/application.properties` for local development.

Recommended local values:

```properties
DB_URL=jdbc:mysql://127.0.0.1:3306/peer_review_db?createDatabaseIfNotExist=true&useSSL=false&allowPublicKeyRetrieval=true&serverTimezone=UTC
DB_USER=root
DB_PASS=your_mysql_password
DB_DRIVER=com.mysql.cj.jdbc.Driver
DB_DIALECT=org.hibernate.dialect.MySQLDialect
PORT=8080
```

## Run Locally

```bash
mvn spring-boot:run
```

The API starts on [http://localhost:8080](http://localhost:8080).

## Build

```bash
mvn clean package
```

## Docker

```bash
docker build -t student-peer-review-backend .
docker run -p 8080:8080 student-peer-review-backend
```

## API Quick Checks
- `GET /api/projects`
- `POST /api/auth/register`
- `POST /api/auth/login`
- `GET /api/projects/{projectId}/reviews`
- `POST /api/projects/{projectId}/reviews`

## Frontend Connection

The frontend can connect to this backend using:

```text
http://localhost:8080/api
```

CORS is already enabled for common local Vite development origins.
