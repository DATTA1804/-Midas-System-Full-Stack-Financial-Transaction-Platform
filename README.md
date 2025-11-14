# 💰 Midas System – Full-Stack Financial Transaction Platform

Midas is a high-performance, event-driven financial transaction processing system built using Spring Boot, Kafka, H2 Database, and REST APIs.
It handles real-time transactions, validates them, updates balances, fetches incentives, and exposes user balance APIs — all in one robust backend service.

---

## 🧠 About the Project

This project simulates a real-world financial backend, showcasing production-grade concepts like:

Event-driven communication with Kafka

Transaction validation and persistence using JPA + H2

External Incentive API integration

REST API for live user balance lookup

Fully automated test-driven workflow (Task 1 to Task 5)

Perfect for backend developers learning Spring Boot, microservices communication, and distributed system design.

---

## 🚀 Features

📥 Kafka Listener
Receives and deserializes incoming transaction messages

✔️ Transaction Validation
Validates sender, recipient, and available balance

💾 H2 Database Integration
Stores users, transactions, and incentive data using Spring Data JPA

🔗 Incentive Service Integration
Calls external /incentive API and updates recipient balance

📊 Balance REST Endpoint
/balance?userId= returns real-time balance for any user

🧪 Comprehensive Testing
Dedicated test suites for each phase (Task 1–5)

⚙️ Clean Architecture
Kafka → Service Layer → JPA → Incentive API → REST Output

---

## 🛠️ Technologies Used

Java 17

Spring Boot 3

Spring Web

Spring Data JPA

Spring Kafka

H2 Database

Testcontainers (Kafka)

Maven

---

## 🧪 Tasks Overview (As per Forage JPMorgan Chase Program)

Task 1 – Setup environment, add dependencies, run TaskOneTests

Task 2 – Implement Kafka Listener & capture initial transaction values

Task 3 – Integrate JPA + H2, validate transactions, store records

Task 4 – Connect Incentive API & update recipient incentives

Task 5 – Expose /balance REST endpoint & run final tests

---

## 📂 Project Modules

src/
 ├── controller/        → Balance API
 ├── consumer/          → Kafka Listener
 ├── entity/            → User + TransactionRecord
 ├── service/           → Validation + Incentive Logic
 ├── repository/        → JPA Repositories
 └── MidasApplication   → Main Spring Boot Runner


---

## ⚡ How It Works

1️⃣ Transaction Received

Kafka → KafkaTransactionListener

2️⃣ Transaction Validated

Check:

sender exists

recipient exists

sender has enough balance

3️⃣ Incentive Retrieved

REST POST → http://localhost:8080/incentive

4️⃣ Transaction Saved

Stored in H2 using JPA

5️⃣ Balance Updated

Balances adjusted + incentive added to recipient

6️⃣ Balance Query

---
