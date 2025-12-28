# 💰 Midas System – Full-Stack Financial Transaction Platform


MIDAS is a high-performance, event-driven financial transaction platform built with Java 25, Spring Boot, Kafka, and React. It processes financial transactions in real-time, integrating with a rewards/incentive system and providing a modern fintech interface.

---

🏗 Architecture

```text
  ┌─────────────────┐      ┌──────────────┐      ┌───────────────┐
  │   Modern React  │◄────►│  Midas Core  │◄────►│   H2 / SQL    │
  │     Frontend    │      │ (Spring Boot)│      │   Database    │
  └─────────────────┘      └──────┬───────┘      └───────────────┘
                                  │
                                  ▼
                          ┌──────────────┐      ┌───────────────┐
                          │    Kafka     │─────►│ Incentive API │
                          │   (Broker)   │      │   (Internal)  │
                          └──────────────┘      └───────────────┘
```

### Data Flow
1. **Frontend** initiates balance lookups or monitors transactions.
2. **Kafka** receives transaction events from external traders (simulated in tests).
3. **Midas Core** consumes Kafka events, validates users and balances.
4. **Incentive API** is called for valid transactions to determine rewards.
5. **Database** persists the `TransactionRecord` and updates `User` balances.

## 🚀 Local Setup

### Prerequisites
- Java 21+ (Java 25 recommended)
- Maven 3.9+
- Node.js 20+
- Kafka Broker (running on localhost:9092)

### Backend
1. Build and install:
   ```bash
   mvn clean install
   ```
2. Run the application:
   ```bash
   mvn spring-boot:run
   ```

### Incentive API
```bash
java -jar services/transaction-incentive-api.jar
```

### Frontend
```bash
cd frontend
npm install
npm run dev
```

## 🐳 Docker Execution

Deploy the entire stack with one command:
```bash
docker-compose up --build
```
- Frontend: `http://localhost`
- Backend: `http://localhost:33400`
- Incentive API: `http://localhost:8080`

## ☁️ Cloud Deployment Plan

### 1. Infrastructure (AWS Example)
- **Compute**: Amazon ECS with Fargate for stateless backend and frontend containers.
- **Database**: Amazon RDS for PostgreSQL (replacing H2) for persistence.
- **Messaging**: Amazon MSK (Managed Streaming for Kafka).
- **Frontend Hosting**: S3 Bucket + CloudFront CDN for static asset delivery.

### 2. Scalability & Resilience
- **Horizontal Scaling**: Backend services scale based on CPU/Memory usage.
- **Kafka Strategy**: Multiple partitions per topic to allow parallel consumption by multiple Midas Core instances.
- **Secrets**: Use AWS Secrets Manager for DB credentials and API keys.

## 📡 API Usage

### Get Balance
**URL**: `/balance`
**Method**: `GET`
**Params**: `userId` (Long)
**Response**:
```json
{
  "amount": 1200.23
}
```

## 🧠 Design Decisions
- **Transactional Safety**: Used `@Transactional` in `DatabaseConduit` to ensure atomicity between user balance updates and transaction record persistence.
- **User Validation**: Silent discard of invalid transactions (as per requirement) ensures system stability under erroneous inputs.
- **Modern UI**: Implemented with glassmorphism and a "Dark Mode" aesthetic using vanilla CSS and Lucide icons for a premium fintech feel.

## ✅ Quality Bar
- **Java 25** ready.
- Clean Architecture (Foundation, Entity, Component, Repository splits).
- Multi-stage Docker optimization for lean production images.

---

🎯 Conclusion

The Midas System is a complete demonstration of a modern event-driven backend, combining Kafka messaging, database persistence, external API integration, and REST services into one cohesive, production-style system.
It’s an excellent project for mastering Spring Boot, microservices, and backend architecture through hands-on learning.

---

