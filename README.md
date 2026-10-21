# Java Professional Spring & Hibernate (JPSH) - Bank Application Labs

This repository contains the progressive implementation of the **Bank Application** across all 5 Spring Framework exercises.

## Java Runtime

The project runs on **Java 21 LTS**. Ensure `JAVA_HOME` is set to your JDK 21 installation (`C:\Program Files\Java\jdk-21`).

## Overview & Branch Structure

The application starts from a standard Spring Framework IoC XML setup and progressively evolves into a modern Spring Boot application with Aspect-Oriented Programming (AOP) and decoupled Spring Events.

Each exercise milestone is developed and maintained on its dedicated branch:

| Branch | Exercise Topic | Key Technologies | Validation Tests |
| :--- | :--- | :--- | :--- |
| **`main`** | Baseline Project | Spring 5, JUnit 5 | Starter setup |
| **`ex1-xml-configuration`** | Exercise 1: XML Configuration | `application-context.xml`, `test-clients.xml`, properties | `BankApplicationTask1..3Tests` |
| **`ex2-annotation-dependencies`** | Exercise 2: Annotation Wiring | `<context:annotation-config />`, `@Autowired` | `BankApplicationTask1..2Tests` |
| **`ex3-java-configuration`** | Exercise 3: Pure Java Config (Zero XML) | `@Configuration`, `@ComponentScan`, `@Bean`, `@PropertySource` | `BankApplicationTask1..2Tests` |
| **`ex4-spring-boot`** | Exercise 4: Spring Boot & Profiles | `@SpringBootApplication`, `application.yml`, `@Profile("dev")` | `BankApplicationTests1..2` |
| **`ex5-aop-events`** | Exercise 5: AOP & Application Events | Spring Boot AOP starter, `@Aspect`, `ApplicationEvent`, SpEL | `BankApplicationTests3..4` |

---

## Lab Documentation

Full guides and detailed task-by-task instructions are located in the [`docs/`](docs/) directory:
* **[`docs/spring_labguide.md`](docs/spring_labguide.md)**: The full lab guide with step-by-step instructions.
* **[`docs/exercise_code_mapping.md`](docs/exercise_code_mapping.md)**: Detailed mapping of files to modify, classes to create, and tests to execute for each task.

---

## Running the Tests

You can run the tests using the Maven wrapper included in the project:

### On Windows:
```cmd
.\mvnw.cmd test
```

### On macOS / Linux:
```bash
./mvnw test
```

To run a specific test class:
```cmd
.\mvnw.cmd test -Dtest=BankApplicationTask1Tests
```
