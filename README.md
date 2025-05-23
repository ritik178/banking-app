# 💰 BankingApp - Spring Boot REST API

A simple Banking Application built using Spring Boot that supports core banking operations like **account creation**, **deposit/withdraw**, **fund transfer**, and **transaction history tracking**. The project uses layered architecture, DTOs for clean separation, and centralized exception handling.

---

## 🔧 Tech Stack

- **Language**: Java
- **Framework**: Spring Boot
- **Database**: MySQL
- **Testing**: Postman
- **Tools**: Maven, Spring Web, Spring Data JPA
- **Error Handling**: `@ControllerAdvice` with custom exception classes

---

## 📁 Project Structure

```plaintext
src/
└── main/
    └── java/
        └── net/
            └── javaguides/
                └── bankingapp/
                    ├── controller/
                    │   └── AccountController.java
                    ├── dto/
                    │   ├── AccountDto.java
                    │   ├── TransactionDto.java
                    │   └── TransferFundDto.java
                    ├── entity/
                    │   ├── Account.java
                    │   └── Transaction.java
                    ├── exception/
                    │   ├── AccountException.java
                    │   ├── ErrorDetails.java
                    │   └── GlobalExceptionHandler.java
                    ├── mapper/
                    │   └── AccountMapper.java
                    ├── repository/
                    │   ├── AccountRepository.java
                    │   └── TransactionRepository.java
                    ├── service/
                    │   ├── AccountService.java
                    │   └── impl/
                    │       └── AccountServiceImpl.java
                    └── BankingAppApplication.java
```

---

## 📌 Features

### ✅ Account Management

- `POST /api/accounts/add` – Add a new bank account
- `GET /api/accounts/{id}` – Fetch account details by ID
- `GET /api/accounts/getAll` – Fetch all accounts
- `DELETE /api/accounts/delete/{id}` – Delete an account

### 💰 Money Operations

- `PUT /api/accounts/deposit/{id}` – Deposit money into an account
- `PUT /api/accounts/widthdraw/{id}` – Withdraw money from an account

### ♻ Transfer Funds

- `POST /api/accounts/transfer` – Transfer funds from one account to another

### 📈 Transaction History

- `GET /api/accounts/transaction/{id}` – Get all transactions related to an account

---

## 🧠 Highlights

- **DTO-Based Design**: Decouples internal models and exposed data
- **Clean Code Structure**: Follows layered architecture with separation of concerns
- **Transaction Tracking**: Each operation is logged as a separate transaction entry
- **Exception Handling**: Managed via `@ControllerAdvice` using `GlobalExceptionHandler`

---

## 📉 Database Configuration (MySQL)

Make sure MySQL is running, and update your `application.properties` file accordingly:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/bankingdb
spring.datasource.username=root
spring.datasource.password=your_password

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
```

---

## 📊 API Testing (Postman)

You can test all the endpoints using Postman or similar tools.

**Sample JSON – Transfer Funds**

```json
{
  "fromAccountId": 1,
  "toAccountId": 2,
  "amount": 1000
}
```

**Sample JSON – Deposit/Withdraw**

```json
{
  "amount": 500
}
```

---

## 📦 Run the Project

Make sure the database is connected and run:

```bash
./mvnw spring-boot:run
```

or

```bash
mvn spring-boot:run
```

---

## 👨‍💻 Author

**Ritik**  
Java | Spring Boot Enthusiast  
Focused on building backend systems with clean architecture and real-world use cases.


 
 
