---
name: java-spring-boot
description: Java and Spring Boot development patterns. Spring Boot 3.x, Spring Security, JPA/Hibernate, reactive programming, and production patterns. Use when building Java backend services, REST APIs, or enterprise applications.
---

# Java & Spring Boot

> Enterprise-grade Java development with Spring Boot 3.x, Spring Security, and modern patterns.

## Core Principles

- **Convention over Configuration**: Spring Boot auto-configuration
- **Production-Ready**: Actuator, health checks, metrics out of the box
- **Type Safety**: Leverage Java's strong type system
- **Dependency Injection**: Constructor injection preferred

---

## Stack Decisions

| Concern | Recommended |
|---------|-------------|
| **Build** | Gradle (Kotlin DSL) or Maven |
| **Java Version** | 21+ (virtual threads, records, sealed classes) |
| **Framework** | Spring Boot 3.x |
| **ORM** | Spring Data JPA + Hibernate |
| **Validation** | Jakarta Validation (Bean Validation 3.0) |
| **Security** | Spring Security 6.x |
| **Testing** | JUnit 5 + Mockito + Testcontainers |
| **API Docs** | SpringDoc OpenAPI |

---

## Project Structure

```
src/
├── main/
│   ├── java/com/example/app/
│   │   ├── config/           # Configuration classes
│   │   ├── controller/       # REST controllers
│   │   ├── service/          # Business logic
│   │   ├── repository/       # Data access
│   │   ├── model/            # JPA entities
│   │   ├── dto/              # Data transfer objects
│   │   ├── exception/        # Custom exceptions
│   │   └── Application.java  # Entry point
│   └── resources/
│       ├── application.yml
│       └── db/migration/     # Flyway migrations
└── test/
```

---

## Key Patterns

- **DTO Pattern**: Separate API shape from entity shape
- **Service Layer**: Business logic in @Service classes
- **Repository Pattern**: Spring Data JPA repositories
- **Global Exception Handling**: @ControllerAdvice
- **Virtual Threads**: `spring.threads.virtual.enabled=true`

---

## Anti-Patterns

| ❌ Don't | ✅ Do |
|----------|-------|
| Business logic in controllers | Use service layer |
| Field injection (@Autowired) | Constructor injection |
| Expose entities in API | Use DTOs |
| Ignore N+1 queries | Use @EntityGraph or JOIN FETCH |
