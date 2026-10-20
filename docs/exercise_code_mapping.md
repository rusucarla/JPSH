# Spring Lab Exercises & Code Mapping Guide

This document provides the verified mapping between each Exercise/Task in `spring_labguide.docx` (`spring_labguide.md`) and the projects, files, Git branches, and test suites found in the workspace subfolders.

---

## 1. Workspace Structure & Two Ways to Complete the Labs

The workspace contains two primary project directories for the lab assignments:

1. **Standalone Folder Workflow**:
   * **Exercises 1, 2, and 3**: Implemented in [`ex1-t1-bank-app`](file:///c:/Users/Carla/Documents/Java(G_M1)/Spring/ex1-t1-bank-app) (a clean starting project prepared for Exercise 1 Task 1).
   * **Exercises 4 and 5**: Implemented in [`spring_boot_labs/bankapp`](file:///c:/Users/Carla/Documents/Java(G_M1)/Spring/spring_boot_labs/bankapp) (a generated Spring Boot project).

2. **Git Branch / Tag Workflow (in `spring_boot_labs/bankapp`)**:
   The instructor created Git tags and branches for every exercise milestone. If you prefer to start each exercise with a clean slate (or if you want to inspect reference solutions):
   * **Start Points / Test Branches**:
     * Exercise 1 Task 1: `git checkout ex1-t1-start` (or branch `ex1-1-tests`)
     * Exercise 1 Task 2: `git checkout ex1.task1` (or branch `ex1-2-tests`)
     * Exercise 1 Task 3: `git checkout ex1.task2` (or branch `ex1-3-tests`)
     * Exercise 2: `git checkout ex2-t1-start`
     * Exercise 3 Task 1: `git checkout ex3-t1-start`
     * Exercise 3 Task 2: `git checkout ex3-t2-start`
     * Exercise 4: `git checkout ex4-start` (commit `b8a5bb9`)
     * Exercise 5: `git checkout origin/ex-5-aop`
   * **Instructor Solution Branches**:
     * Exercise 1: branch `ex1` (tags: `ex1.task1`, `ex1.task2`, `ex1.task3`)
     * Exercise 2: branch `annotations-based`
     * Exercise 3: branch `ex3-java-based`
     * Exercise 4: branch `ex4-spring-boot`
     * Exercise 5: branch `ex-5-aop`

---

## 2. Comprehensive Task-by-Task Mapping Matrix

| Exercise & Task | Lab Guide Topic | Project Folder | Git Start Tag / Branch | Files to Create / Modify / Delete | Verification Test Class | Reference Solution Branch |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Ex 1: Task 1** | Set up banking via XML & Bean wiring | `ex1-t1-bank-app` | `ex1-t1-start` / `ex1-1-tests` | **Modify**: `application-context.xml`, `BankApplication.java` | `BankApplicationTask1Tests` | `ex1.task1` |
| **Ex 1: Task 2** | Configure Reporting Service in XML | `ex1-t1-bank-app` | `ex1.task1` / `ex1-2-tests` | **Modify**: `application-context.xml`, `BankApplication.java` | `BankApplicationTask2Tests` | `ex1.task2` |
| **Ex 1: Task 3** | Configure Test Clients & Properties | `ex1-t1-bank-app` | `ex1.task2` / `ex1-3-tests` | **Create**: `test-clients.xml`, `clients.properties`<br>**Modify**: `BankApplication.java`, `Client.java` | `BankApplicationTask3Tests` | `ex1.task3` |
| **Ex 2: Task 1** | Annotation-Based Dependencies (`@Autowired`) | `ex1-t1-bank-app` | `ex2-t1-start` | **Modify**: `application-context.xml`, `BankingImpl.java`, `BankReportServiceImpl.java` | `BankApplicationTask1Tests`, `Task2Tests` | `annotations-based` |
| **Ex 3: Task 1** | Java-Based Config (`@Configuration`, `@Service`) | `ex1-t1-bank-app` | `ex3-t1-start` | **Modify**: `MapClientRepository.java`, `BankingImpl.java`, `BankReportServiceImpl.java`, `BankApplication.java`<br>**Delete**: `application-context.xml` | `BankApplicationTask1Tests`, `Task2Tests` | `ex-3-t1-finished` |
| **Ex 3: Task 2** | Java-Based Config for Demo Clients (`@Bean`, `@PropertySource`) | `ex1-t1-bank-app` | `ex3-t2-start` | **Modify**: `BankApplication.java`<br>**Delete**: `test-clients.xml` | `BankApplicationTask1Tests`, `Task2Tests` | `ex3-java-based` |
| **Ex 4: Task 1** | Switch to Spring Boot Project | `spring_boot_labs/bankapp` | `d86d8a3` | Explore generated Spring Boot structure and dependencies in `pom.xml` | N/A (Project review) | `ex4-spring-boot` |
| **Ex 4: Task 2** | Profiles Configuration (`application.yml`) | `spring_boot_labs/bankapp` | `cee5f23` | **Rename**: `application.properties` &rarr; `application.yml`<br>**Modify**: `application.yml`, `DemoBankInitializationService.java`, `BankApplication.java` | `BankApplicationTests1` | `ex4-spring-boot` |
| **Ex 4: Task 3** | Custom Feed File Name (`@Value`) | `spring_boot_labs/bankapp` | `b8a5bb9` (`ex4-start`) | **Modify**: `application.yml`, `DemoBankInitializationService.java` | `BankApplicationTests2` | `ex4-spring-boot` |
| **Ex 5: Task 1** | Banking Operations Service | `spring_boot_labs/bankapp` | `origin/ex-5-aop` | **Modify**: `BankingOperationsServiceImpl.java` (add `@Service`) | `BankApplicationTests3` | `ex-5-aop` |
| **Ex 5: Task 2** | Audit Service with AspectJ AOP | `spring_boot_labs/bankapp` | `origin/ex-5-aop` | **Modify**: `pom.xml`<br>**Create**: `Audit.java`, `WithdrawState.java`, `AuditService.java`, `AuditAspect.java` | `BankApplicationTests4` | `ex-5-aop` |
| **Ex 5: Task 3** | Audit Service Events (`ApplicationEvent`, `@EventListener`) | `spring_boot_labs/bankapp` | `origin/ex-5-aop` | **Create**: `AccountEvent.java`, `BalanceEvent.java`, `DepositEvent.java`, `WithdrawEvent.java`<br>**Delete**: `WithdrawState.java`<br>**Modify**: `Audit.java`, `AuditService.java`, `AuditAspect.java`, `BankApplicationTests4.java` | `BankApplicationTests4` | `ex-5-aop` |
| **Ex 5: Task 4** | Filtering Audit Events (SpEL & Condition) | `spring_boot_labs/bankapp` | `origin/ex-5-aop` | **Modify**: `application.yml`, `AuditService.java`<br>**Create**: `EventConditionFilter.java` | `BankApplicationTests4` | `ex-5-aop` |

---

## 3. Detailed Per-Exercise Instructions & Code Locations

### Exercise 1: XML Configuration

#### Task 1: Set up Banking
* **Working Directory**: `ex1-t1-bank-app`
* **Files to Modify**:
  * [`src/main/resources/application-context.xml`](file:///c:/Users/Carla/Documents/Java(G_M1)/Spring/ex1-t1-bank-app/src/main/resources/application-context.xml):
    Add `<bean id="clientRepository" class="com.luxoft.bankapp.service.storage.MapClientRepository" />` and `<bean id="banking" class="com.luxoft.bankapp.service.BankingImpl" autowire="byType" />`.
  * [`src/main/java/BankApplication.java`](file:///c:/Users/Carla/Documents/Java(G_M1)/Spring/ex1-t1-bank-app/src/main/java/BankApplication.java):
    In `main()`, initialize `ApplicationContext context = new ClassPathXmlApplicationContext("application-context.xml");`.
    Update `initialize` method signature: `public static Banking initialize(ApplicationContext context)`.
    Replace `Banking banking = new BankingImpl(); banking.setRepository(repository);` with `Banking banking = (Banking) context.getBean("banking");`.
* **Validation**: Run [`src/test/java/BankApplicationTask1Tests.java`](file:///c:/Users/Carla/Documents/Java(G_M1)/Spring/ex1-t1-bank-app/src/test/java/BankApplicationTask1Tests.java).

#### Task 2: Configure Reporting
* **Files to Modify**:
  * `src/main/resources/application-context.xml`:
    Add `<bean id="bankReport" class="com.luxoft.bankapp.service.BankReportServiceImpl" autowire="byType" />`.
  * `src/main/java/BankApplication.java`:
    Update `bankReportsDemo(ApplicationContext context)` to fetch `BankReportService reportService = (BankReportService) context.getBean("bankReport");`.
* **Validation**: Run [`src/test/java/BankApplicationTask2Tests.java`](file:///c:/Users/Carla/Documents/Java(G_M1)/Spring/ex1-t1-bank-app/src/test/java/BankApplicationTask2Tests.java).

#### Task 3: Configure Clients
* **Files to Create**:
  * `src/main/resources/test-clients.xml`:
    Import `application-context.xml`. Define beans: `savingAccount1` (balance 1000), `checkingAccount1` (overdraft 1000), `client1` (name `${client1}`, gender, accounts, repository), `checkingAccount2` (overdraft 1500), `client2` (name `${client2}`).
    Configure `PropertySourcesPlaceholderConfigurer` with location `clients.properties`.
  * `src/main/resources/clients.properties`:
    Add `client1=Jonny Bravo`, `client2=Adam Budzinski`, `client3=Anna Smith`.
* **Files to Modify**:
  * [`src/main/java/com/luxoft/bankapp/model/Client.java`](file:///c:/Users/Carla/Documents/Java(G_M1)/Spring/ex1-t1-bank-app/src/main/java/com/luxoft/bankapp/model/Client.java): Add setter for accounts list.
  * `src/main/java/BankApplication.java`: Load `test-clients.xml` in context; in `initialize()`, retrieve `client1` and `client2` from `context.getBean(...)`.
* **Validation**: Run `BankApplicationTask1Tests`, `BankApplicationTask2Tests`, and `BankApplicationTask3Tests`.

---

### Exercise 2: Annotation-Based Dependencies

#### Task 1: Annotation Based Dependencies
* **Working Directory**: `ex1-t1-bank-app`
* **Files to Modify**:
  * `src/main/resources/application-context.xml`:
    Add `<context:annotation-config />`. Remove `autowire` attributes and explicit repository properties.
  * [`src/main/java/com/luxoft/bankapp/service/BankingImpl.java`](file:///c:/Users/Carla/Documents/Java(G_M1)/Spring/ex1-t1-bank-app/src/main/java/com/luxoft/bankapp/service/BankingImpl.java):
    Annotate `private ClientRepository repository;` with `@Autowired`.
  * [`src/main/java/com/luxoft/bankapp/service/BankReportServiceImpl.java`](file:///c:/Users/Carla/Documents/Java(G_M1)/Spring/ex1-t1-bank-app/src/main/java/com/luxoft/bankapp/service/BankReportServiceImpl.java):
    Annotate `repository` / `storage` field with `@Autowired`.
* **Validation**: Tests from `BankApplicationTask1Tests` and `BankApplicationTask2Tests` must pass.

---

### Exercise 3: Java-Based Configuration (No XML)

#### Task 1: Java Based Configuration
* **Files to Modify**:
  * Annotate `MapClientRepository`, `BankingImpl`, and `BankReportServiceImpl` with `@Service`.
  * `BankApplication.java`:
    Add `@Configuration` and `@ComponentScan("com.luxoft.bankapp")`.
    In `main()`, replace `ClassPathXmlApplicationContext` with `new AnnotationConfigApplicationContext(BankApplication.class)`.
* **Files to Delete**:
  * Delete `src/main/resources/application-context.xml`.
* **Validation**: Tests from `BankApplicationTask1Tests` and `BankApplicationTask2Tests` must pass.

#### Task 2: Java Based Configuration (for test clients)
* **Files to Modify**:
  * `BankApplication.java`:
    Add `@PropertySource("classpath:clients.properties")`.
    Inject `ApplicationContext` and `Environment`.
    Add `@Bean` methods: `checkingAccount2`, `client2`, `checkingAccount1`, `client1`, `savingAccount1`.
    Update `initialize`, `bankReportsDemo`, `bankingServiceDemo`, `workWithExistingClients`.
* **Files to Delete**:
  * Delete `src/main/resources/test-clients.xml`.
* **Validation**: All tests must pass.

---

### Exercise 4: Switch to Spring Boot & Profiles

* **Working Directory**: [`spring_boot_labs/bankapp`](file:///c:/Users/Carla/Documents/Java(G_M1)/Spring/spring_boot_labs/bankapp)

#### Task 2: Profiles Configuration
* **Files to Modify**:
  * Rename `application.properties` to `application.yml` and add `dev` and `prod` profiles with `debug` toggles.
  * [`DemoBankInitializationService.java`](file:///c:/Users/Carla/Documents/Java(G_M1)/Spring/spring_boot_labs/bankapp/src/main/java/com/luxoft/bankapp/service/demo/DemoBankInitializationService.java):
    Add `@Profile("dev")`. Autowire `BankFeedService`. Add `@PostConstruct` on `createClientsForDemo()` to call `feedService.loadFeed(new File("demo.feed"))`.
  * [`BankApplication.java`](file:///c:/Users/Carla/Documents/Java(G_M1)/Spring/spring_boot_labs/bankapp/src/main/java/com/luxoft/bankapp/BankApplication.java):
    Simplify `main()` to only call `SpringApplication.run(BankApplication.class, args);`.
* **Validation**: Run [`BankApplicationTests1.java`](file:///c:/Users/Carla/Documents/Java(G_M1)/Spring/spring_boot_labs/bankapp/src/test/java/com/luxoft/bankapp/BankApplicationTests1.java).

#### Task 3: Custom Feed File Name
* **Files to Modify**:
  * `DemoBankInitializationService.java`: Add `@Value("${feed.filename}") private String fileName;` and use it in `createClientsForDemo()`.
  * `application.yml`: Add `feed.filename: demo.feed`.
* **Validation**: Run [`BankApplicationTests2.java`](file:///c:/Users/Carla/Documents/Java(G_M1)/Spring/spring_boot_labs/bankapp/src/test/java/com/luxoft/bankapp/BankApplicationTests2.java).

---

### Exercise 5: AOP and Events

* **Working Directory**: [`spring_boot_labs/bankapp`](file:///c:/Users/Carla/Documents/Java(G_M1)/Spring/spring_boot_labs/bankapp) *(branch `ex-5-aop`)*

#### Task 1: Banking Operations
* **Files to Modify**:
  * [`BankingOperationsServiceImpl.java`](file:///c:/Users/Carla/Documents/Java(G_M1)/Spring/spring_boot_labs/bankapp/src/main/java/com/luxoft/bankapp/service/operations/BankingOperationsServiceImpl.java): Annotate with `@Service`.
* **Validation**: Run `BankApplicationTests3`.

#### Task 2: Audit Service with AspectJ
* **Files to Modify / Create**:
  * [`pom.xml`](file:///c:/Users/Carla/Documents/Java(G_M1)/Spring/spring_boot_labs/bankapp/pom.xml): Add `spring-boot-starter-aop`.
  * Create package `com.luxoft.bankapp.service.audit`:
    * `Audit.java`: Interface defining `auditDeposit`, `auditWithdraw`, `auditBalance`.
    * `WithdrawState.java`: Enum (`TRYING`, `SUCCESSFUL`, `FAILED`).
    * `AuditService.java`: Service implementing `Audit`.
    * `AuditAspect.java`: `@Configuration` and `@Aspect` class with `@Pointcut`, `@Before("anyDeposit()")`, `@Before("anyBalance()")`, and `@Around("anyWithdraw()")`.
* **Validation**: Run `BankApplicationTests4`.

#### Task 3: Audit Service Events
* **Files to Create**:
  * Create package `com.luxoft.bankapp.service.audit.events`:
    * `AccountEvent.java`: Abstract class extending `ApplicationEvent`.
    * `BalanceEvent.java`, `DepositEvent.java`, `WithdrawEvent.java`: Event classes extending `AccountEvent`. `WithdrawEvent` has an inner `enum State { TRYING, SUCCESSFUL, FAILED }`.
* **Files to Delete / Modify**:
  * Delete `WithdrawState.java`.
  * `Audit.java`: Change signatures to receive event objects.
  * `AuditService.java`: Annotate methods with `@EventListener`.
  * `AuditAspect.java`: Autowire `ApplicationContext` and publish events with `applicationContext.publishEvent(...)`.
  * `BankApplicationTests4.java`: Update test assertions to match event-driven audit.
* **Validation**: Run `BankApplicationTests4`.

#### Task 4: Filtering Audit Events
* **Files to Modify / Create**:
  * `application.yml`: Add `audit.amount.deposit: 99` and `audit.amount.withdrawal: 99`.
  * Create `EventConditionFilter.java`: `@Component` reading the `@Value("${audit.amount...}")` properties.
  * `AuditService.java`: Add SpEL condition to `@EventListener`:
    `condition = "#event.amount >= @eventConditionFilter.depositLimit"`.
* **Validation**: Run `BankApplicationTests4`.

---

## 4. Lecture Demo Examples Mapping

For reference while solving the labs, the slide topics map directly to the demo projects:

| Presentation Slide Deck | Folder | Contents |
| :--- | :--- | :--- |
| **`Core-IoC1.pdf`** | [`SpringIoC/src/main/java/com/luxoft/springioc/example01`](file:///c:/Users/Carla/Documents/Java(G_M1)/Spring/SpringIoC/src/main/java/com/luxoft/springioc) through `example24` | Core IoC concepts: `BeanFactory`, `ApplicationContext`, constructor injection, setter injection, autowiring (`byType`, `byName`), XML namespaces (`c:`, `p:`), collections wiring, inner beans, bean inheritance. |
| **`Core-IoC2.pdf`** | [`SpringIoC/src/main/java/com/luxoft/springioc/example25`](file:///c:/Users/Carla/Documents/Java(G_M1)/Spring/SpringIoC/src/main/java/com/luxoft/springioc) through `example41` | Advanced IoC & Annotations: `@Autowired`, `@Qualifier`, `@Resource`, `@PostConstruct`, `@PreDestroy`, `@Configuration`, `@Bean`, `@ComponentScan`, `@PropertySource`, `Environment`, SpEL, Application Events (`ApplicationEventPublisher`, `@EventListener`). |
| **`SpringBoot.pdf`** | [`spring_boot_examples/profiles`](file:///c:/Users/Carla/Documents/Java(G_M1)/Spring/spring_boot_examples/profiles) & [`yaml`](file:///c:/Users/Carla/Documents/Java(G_M1)/Spring/spring_boot_examples/yaml) | Spring Boot setup, `@SpringBootApplication`, profiles (`@Profile`, `spring.profiles.active`), and YAML hierarchy configuration. |
