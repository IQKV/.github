## 🚀 Key Value Platform

**[Microservices Platform](https://github.com/IQKV/microservices-platform)** - SaaS foundation with user management, payments, CRM, and multi-tenant operations.

**Tech Stack**: Java **21** + Spring Boot **4.0**, React **19** + TypeScript, PostgreSQL, RabbitMQ, Redis  
**Key Features**: JWT authentication, Stripe payments, CRM pipeline, multi-tenant isolation  
**Deployment**: Kubernetes + Helm charts, Docker containers, cloud-agnostic architecture  
**Links**: [iqkv.com](https://iqkv.com) | [github.com/IQKV](https://github.com/IQKV) | Apache License

<details>
<summary><strong>💼 Business Capabilities</strong></summary>

**👥 User Management & Authentication**

- User registration, login, and email verification
- Role-based access control with tenant isolation
- Password reset and account security
- Organization management and user preferences

**💳 Payment Processing & Billing**

- Stripe integration with payment intents and webhooks
- Merchant onboarding via Stripe Connect
- Subscription management with plans and invoicing
- Multi-gateway support (Stripe, PayPal, Square, Braintree)
- Automated refund processing and payout tracking

**📊 CRM & Lead Management**

- Lead capture and pipeline management
- Contact organization and activity tracking
- Follow-up scheduling and conversion analytics
- Dashboard with KPIs and performance metrics

**⚙️ Platform Infrastructure**

- API gateway with rate limiting and circuit breakers
- Multi-tenant data isolation (schema-per-tenant)
- JWT-based authentication across all services
- Reactive programming for high-throughput scenarios

</details>

<details>
<summary><strong>🏗️ Architecture & Implementation</strong></summary>

**Backend Services**: User Service (authentication), Gateway Service (routing), Billing Service (payments), CRM Services (leads, contacts, pipeline)

**Frontend Applications**: React portal with authentication, billing management, CRM dashboard, and admin panels

**Infrastructure**: PostgreSQL databases, Redis caching, Docker containers, Kubernetes deployment

**Technical Stack**:

- **Backend**: Java 21, Spring Boot 4.0, Spring Cloud Gateway, PostgreSQL, Redis, RabbitMQ
- **Frontend**: React 19, TypeScript, Vite, Mantine UI, TanStack Router/Query
- **Security**: JWT with RSA256, OAuth2 Resource Server, role-based access control
- **Operations**: Docker containers, Kubernetes manifests, OpenTelemetry observability
- **Testing**: JUnit 5, Testcontainers, Playwright, comprehensive test coverage

</details>

<details>
<summary><strong>📁 Repository Structure & Standards</strong></summary>

**Repository Organization**:

- **Platform Services**: Complete microservices with authentication, billing, CRM, and gateway
- **Frontend Applications**: React portals for user management, billing, and CRM operations
- **Development Tools**: Docker Compose setup, CI/CD pipelines, code quality tools
- **Documentation**: Architecture guides, API documentation, deployment instructions

**Development Standards**:

- **Language**: Java/Kotlin with Spring Boot, TypeScript with React
- **Architecture**: Domain-driven design, clean architecture, microservices patterns
- **Quality**: SonarQube, PMD, CheckStyle, SpotBugs code analysis
- **Testing**: Unit tests, integration tests, end-to-end tests, architecture validation
- **CI/CD**: Automated builds, testing, security checks, and deployment pipelines

</details>
