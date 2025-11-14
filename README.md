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
