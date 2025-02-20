# 🍃 Spring Boot Specialist

## 📌 Overview
This repository contains a set of modules and APIs developed with Spring Boot, organized to provide security, product management, order processing, localization, and shared library functionalities.

The project follows best practices for architecture and development with Spring Boot, using patterns such as MVC, REST API, JWT authentication, and other modern backend technologies. Additionally, it is designed to be scalable, modular, and easy to maintain.

---

### 📂 Project Structure
#### **Arquitetura-Spring**: Contains general project patterns and configurations, including:
  - Database configuration
  - Logging and monitoring
  - Environment setup (dev, staging, production)
  - Development best practices

#### **SpringBoot-Security**: Security implementation using Spring Security with support for:
  - JWT for authentication and authorization
  - User and permission management
  - OAuth2 integration (optional)

#### **Resource-Server**: Resource server responsible for providing authentication tokens and managing sessions, ensuring that other services are protected by authentication.

#### **Library-API**: Shared library between the project's APIs, containing:
  - Common utilities (validations, converters, error handlers)
  - Support classes
  - Reusable data models

#### **Produtos-API**: API dedicated to product management, including:
  - Product creation, editing, deletion, and listing
  - Support for filters and pagination
  - Integration with other APIs, such as Orders

---

## ✅ Requirements
Before starting the project, ensure you have the following requirements installed in your development environment:

- Java 17+ (recommended version for Spring Boot 3 support)
- Spring Boot 3+
- Maven 3.6+ or Gradle 7+
- Docker and Docker Compose (optional but recommended for local environments)
- PostgreSQL or MySQL database
- Redis (for caching and authentication, if necessary)
- API testing tools such as Postman or Insomnia

---

## ⚙️ Setup and Execution
### 🔽 Clone the Repository
To obtain a local copy of the project, run the following command:
```bash
git clone <REPOSITORY_URL>
cd Spring-Boot-Specialist
```

### 🗄️ Database Configuration
Database configurations should be set in the `application.properties` or `application.yml` file located within each module. Here is an example configuration for PostgreSQL:
```properties
spring.datasource.url=jdbc:postgresql://localhost:5432/mydatabase
spring.datasource.username=user
spring.datasource.password=password
spring.jpa.hibernate.ddl-auto=update
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.PostgreSQLDialect
```
For MySQL, the configuration would be:
```properties
spring.datasource.url=jdbc:mysql://localhost:3306/mydatabase
spring.datasource.username=user
spring.datasource.password=password
spring.jpa.hibernate.ddl-auto=update
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQL8Dialect
```
If using Docker, you can quickly start a database with:
```bash
docker-compose up -d
```

### 🔧 Build and Run
Using Maven:
```bash
mvn clean install
mvn spring-boot:run -pl <module>
```

Using Gradle:
```bash
gradle build
java -jar <module>/build/libs/<module>.jar
```

### 🐳 Run with Docker (Optional)
If you want to run the application using Docker, a `Dockerfile` and `docker-compose.yml` are available to facilitate deployment.
```bash
docker-compose up -d
```
This will start the necessary containers for running the application.

## 🧪 Testing
The application includes a set of automated tests to ensure code quality. To run the tests, use:
```bash
mvn test # For Maven
gradle test # For Gradle
```
---

## 📖 API Documentation
The project uses Swagger for documenting REST APIs. After starting the application, access:
```
http://localhost:8080/swagger-ui.html
```
to view and test available endpoints.

---

## 🚀 Deployment in Production
To deploy the application in a production environment, consider the following best practices:
- Use a managed database, such as AWS RDS or Azure Database
- Set up a monitoring system, such as Prometheus + Grafana
- Implement a reverse proxy, such as Nginx or Traefik
- Use a centralized logging service, such as ELK Stack (Elasticsearch, Logstash, and Kibana)


