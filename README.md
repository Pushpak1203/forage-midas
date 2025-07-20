# Midas Core

Midas Core is a key component of the **Midas** system, responsible for receiving, validating, and recording financial transactions. It acts as the central processing unit for transactional data, integrating seamlessly with Kafka, SQL databases, and RESTful services.

---

## 🛠 Tech Stack

- **Java 17**
- **Spring Boot 3.2.5**
- **Apache Kafka (via Spring Kafka 3.1.4)**
- **JPA (Spring Data JPA)**
- **H2 In-Memory Database**
- **REST API (Spring Web)**
- **Testcontainers (Kafka)**
- **JUnit (Spring Boot Test, Kafka Test)**

---

## 🚀 Features

- ✅ Kafka consumer to receive transaction events  
- ✅ Validates incoming financial transaction data  
- ✅ Persists data using JPA into an SQL database  
- ✅ Provides REST API endpoints to access or test transactions  
- ✅ In-memory H2 database for fast development and testing  
- ✅ Testcontainers support for Kafka integration tests

---

## 📦 Dependencies (from `pom.xml`)

```xml
<dependencies>
    <!-- Spring Core Dependencies -->
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-web</artifactId>
        <version>3.2.5</version>
    </dependency>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-data-jpa</artifactId>
        <version>3.2.5</version>
    </dependency>

    <!-- Kafka Integration -->
    <dependency>
        <groupId>org.springframework.kafka</groupId>
        <artifactId>spring-kafka</artifactId>
        <version>3.1.4</version>
    </dependency>

    <!-- In-Memory Database -->
    <dependency>
        <groupId>com.h2database</groupId>
        <artifactId>h2</artifactId>
        <version>2.2.224</version>
        <scope>runtime</scope>
    </dependency>

    <!-- Testing -->
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-test</artifactId>
        <version>3.2.5</version>
        <scope>test</scope>
    </dependency>
    <dependency>
        <groupId>org.springframework.kafka</groupId>
        <artifactId>spring-kafka-test</artifactId>
        <version>3.1.4</version>
        <scope>test</scope>
    </dependency>
    <dependency>
        <groupId>org.testcontainers</groupId>
        <artifactId>kafka</artifactId>
        <version>1.19.1</version>
        <scope>test</scope>
    </dependency>
</dependencies>
```

---

## 📂 Project Structure

```
forage-midas/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/jpmc/midascore/
│   │   │       ├── controller/
│   │   │       ├── model/
│   │   │       ├── repository/
│   │   │       ├── service/
│   │   │       └── MidasCoreApplication.java
│   │   └── resources/
│   │       ├── application.properties
│   └── test/
├── pom.xml
└── README.md
```

---

## 🧪 Running the Project

### 🖥️ Prerequisites

- Java 17
- Maven 3.8+
- Kafka (for full functionality)

### ▶️ To Run Locally:

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/forage-midas.git
   cd forage-midas
   ```

2. Start Kafka (locally or using Docker)

3. Run the application:
   ```bash
   mvn spring-boot:run
   ```

4. The service will be available at:  
   `http://localhost:8080`

---

## 🧪 Running Tests

```bash
mvn test
```

Testcontainers will spin up Kafka for integration tests automatically.

---

## 📬 API and Kafka Details

- **Kafka Topic:** `general.kafka-topic` (configured in `application.properties`)
- **REST API Endpoint (Sample):**
  ```
  POST /api/transactions
  ```

---
