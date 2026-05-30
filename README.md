# Digital Payment Config Repository

Centralised Git-backed configuration repository for the Digital Payment Platform microservices ecosystem using Spring Cloud Config Server.

This repository stores externalised configuration files for all microservices, enabling centralised configuration management, environment-specific properties, and cloud-native-configuration distribution.

---

# 🚀 Purpose

This repository acts as the single source of truth for configuration management across all microservices inside the Digital Payment Platform.

The configurations are consumed dynamically through:

* Spring Cloud Config Server
* Eureka-based microservices
* API Gateway
* Kafka consumers
* Distributed services

---

# 🏗️ Architecture Flow

```text
GitHub Config Repository
           ↓
Spring Cloud Config Server
           ↓
Microservices
```

---

# 📁 Repository Structure

```text
digital-payment-config-repo/
│
├── application.yml
├── api-gateway.yml
├── auth-service.yml
├── wallet-service.yml
├── payment-processing-service.yml
├── transaction-service.yml
├── notification-service.yml
├── fraud-detection-service.yml
├── analytics-service.yml
│
├── auth-service-dev.yml
├── auth-service-qa.yml
├── auth-service-prod.yml
│
└── README.md
```

---

# 📌 Configuration Responsibilities

This repository manages:

* Server ports
* Database configurations
* Kafka configurations
* Redis configurations
* JWT configurations
* Eureka client settings
* Logging configuration
* Monitoring configuration
* Environment-specific properties
* External service URLs

---

# 🌍 Supported Environments

Environment-based configuration profiles:

```text
dev
qa
uat
prod
```

Example:

```text
auth-service-dev.yml
auth-service-qa.yml
auth-service-prod.yml
```

---

# ⚙️ Example Configuration

## auth-service.yml

```yaml
server:
  port: 8081

spring:
  datasource:
    url: jdbc:postgresql://localhost:5432/auth_db
    username: postgres
    password: postgres

  jpa:
    hibernate:
      ddl-auto: update

jwt:
  secret: my-secret-key
```

---

# 🔄 Spring Cloud Config Integration

Microservices connect to the Config Server using:

```yaml
spring:
  config:
    import: optional:configserver:http://localhost:8888
```

The Config Server fetches configuration files directly from this repository.

---

# 🔐 Security Recommendations

Sensitive production secrets should not be stored directly in plain text.

Recommended enterprise solutions:

* HashiCorp Vault
* AWS Secrets Manager
* Kubernetes Secrets
* Encrypted Config Server
* Environment variables

---

# ☸️ Cloud-Native Support

This repository is designed for:

* Docker deployments
* Kubernetes deployments
* CI/CD pipelines
* Cloud-native microservices
* GitOps workflows
* Dynamic scaling environments

---

# 🧠 Enterprise Concepts Demonstrated

* Spring Cloud Config Server
* Externalised Configuration
* Git-backed Configuration Management
* Environment-based Configuration
* Centralised Configuration Management
* Distributed Systems Architecture
* Cloud-Native Configuration


# 📄 License

MIT License
