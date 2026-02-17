# digibnk Platform – Distributed Transaction Processing System

This platform is a cloud-native, distributed transaction processing system designed using
Java 21 microservices. It demonstrates modern enterprise architecture including
SAGA-based transactions, event-driven communication, secure APIs, and full observability.

The system is designed to simulate a real-world financial transaction environment
where consistency, resilience, security and scalability are critical.

---

## Core Architecture Principles

- Microservices based
- Database per service
- Event-driven communication using Kafka
- Strong consistency for financial transactions using SAGA
- Stateless services with horizontal scalability
- OAuth2 and JWT for security
- Cloud-native deployment using Docker and Kubernetes

---

## High Level Flow

Client → API Gateway → Transaction Service → Account Service  
Transaction Service → Kafka → Fraud Service → Notification Service  
Transaction Service → Ledger Service  

Authentication is handled via OAuth2 / JWT using Keycloak.

---

## Core Services

| Service | Responsibility |
|--------|----------------|
| core-gateway | API gateway, JWT validation, rate limiting |
| auth-service | OAuth2, Keycloak, SSO |
| customer-service | Customer and KYC management |
| account-service | Account balances, ACID transactions |
| transaction-service | Money transfer orchestration (SAGA) |
| fraud-service | Fraud validation using events |
| notification-service | Sends notifications |
| ledger-service | Immutable transaction log |
| common-lib | Shared DTOs, Protos and security |

---

## Key Technology Choices

| Area | Technology |
|------|-----------|
| Language | Java 21 |
| Framework | Spring Boot 3.x |
| Messaging | Kafka |
| API | REST + gRPC |
| Security | JWT + OAuth2 + Keycloak |
| Database | PostgreSQL |
| Schema | Liquibase |
| Resilience | Resilience4j |
| Scheduling | ShedLock |
| Mapping | MapStruct |
| Observability | Zipkin + logging |
| Deployment | Docker + Kubernetes |
| CI/CD | GitHub Actions |
