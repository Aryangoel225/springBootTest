# 📘 Spring Boot Backend Notes

This document contains clean, modular notes for a full-stack Java Spring Boot backend.
---

## 📂 Structure Overview

Each section maps to a typical Java Spring Boot project structure:

src/main/java/com/example/demo/
│
├── student/
│ ├── Student.java // Entity (Model)
│ ├── StudentRepository.java // Repository (Data Access Layer)
│ ├── StudentService.java // Service Layer
│ ├── StudentController.java // API Layer (REST Controller)
│ └── StudentConfig.java // Configuration (Data Seeding)

---

## 📌 Sections Included

### 1. 🌐 API Layer – `StudentController.java`

- Handles HTTP requests: `GET`, `POST`, `PUT`, `DELETE`
- Uses `@RestController`, `@RequestMapping`, `@RequestBody`, `@PathVariable`
- Forwards client requests to the service layer
- Manages routing and simple input extraction

### 2. 🧠 Service Layer – `StudentService.java`

- Contains core **business logic**
- Validates inputs and throws exceptions when needed
- Uses `@Service`, `@Transactional`, and dependency injection
- Communicates with the repository to fetch or modify data

### 3. 🗂️ Data Access Layer – `StudentRepository.java`

- Interface that extends `JpaRepository`
- Supports auto-generated query methods like `findByEmail`, `existsById`
- Abstracts all SQL/database operations
- Enables easy unit testing and separation of concerns

### 4. 🧱 Entity Layer – `Student.java`

- Defines the structure of the database table (`@Entity`, `@Table`)
- Includes a dynamic `@Transient` field for `age`
- Uses annotations like `@Id`, `@GeneratedValue`, `@SequenceGenerator`
- Contains constructors, getters/setters, and `toString()`

### 5. 🧪 Configuration & Data Seeding – `StudentConfig.java`

- Seeds sample data on app startup using `CommandLineRunner`
- Useful during development and manual testing
- Marked with `@Configuration` and `@Bean`

---

## 🐘 PostgreSQL Configuration Notes

### 🔧 `application.properties`
```properties
spring.datasource.url=jdbc:postgresql://localhost:5432/studentdb
spring.datasource.username=your_pg_username
spring.datasource.password=your_pg_password
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
