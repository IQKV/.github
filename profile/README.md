## IQ Key Value Platform

**[Production-Ready Microservices Platform](https://github.com/IQKV/quickstart-microservices-platform)**

Complete microservices foundation for building SaaS applications. Handles user management, payments, CRM, and multi-tenant operations with Java 21 and React 19.

### Business Capabilities

**User Management & Authentication**

- User registration, login, and email verification
- Role-based access control with tenant isolation
- Password reset and account security
- Organization management and user preferences

**Payment Processing & Billing**

- Stripe integration with payment intents and webhooks
- Merchant onboarding via Stripe Connect
- Subscription management with plans and invoicing
- Multi-gateway support (Stripe, PayPal, Square, Braintree)
- Automated refund processing and payout tracking

**CRM & Lead Management**

- Lead capture and pipeline management
- Contact organization and activity tracking
- Follow-up scheduling and conversion analytics
- Dashboard with KPIs and performance metrics

**Platform Infrastructure**

- API gateway with rate limiting and circuit breakers
- Multi-tenant data isolation (schema-per-tenant)
- JWT-based authentication across all services
- Reactive programming for high-throughput scenarios

### Architecture

**Backend Services**: User Service (authentication), Gateway Service (routing), Billing Service (payments), CRM Services (leads, contacts, pipeline)

**Frontend Applications**: React portal with authentication, billing management, CRM dashboard, and admin panels

**Infrastructure**: PostgreSQL databases, Redis caching, Docker containers, Kubernetes deployment

### Technical Implementation

**Backend**: Java 21, Spring Boot 3.5, Spring Cloud Gateway, PostgreSQL, Redis, RabbitMQ
**Frontend**: React 19, TypeScript, Vite, Mantine UI, TanStack Router/Query
**Security**: JWT with RSA256, OAuth2 Resource Server, role-based access control
**Operations**: Docker containers, Kubernetes manifests, OpenTelemetry observability
**Testing**: JUnit 5, Testcontainers, Playwright, comprehensive test coverage

### Repository Structure

**Platform Services**: Complete microservices with authentication, billing, CRM, and gateway
**Frontend Applications**: React portals for user management, billing, and CRM operations  
**Development Tools**: Docker Compose setup, CI/CD pipelines, code quality tools
**Documentation**: Architecture guides, API documentation, deployment instructions

### Development Standards

**Language**: Java/Kotlin with Spring Boot, TypeScript with React
**Architecture**: Domain-driven design, clean architecture, microservices patterns
**Quality**: SonarQube, PMD, CheckStyle, SpotBugs code analysis
**Testing**: Unit tests, integration tests, end-to-end tests, architecture validation
**CI/CD**: Automated builds, testing, security checks, and deployment pipelines

### Links

**Platform**: [iqkv.com](https://iqkv.com) | **Organization**: [github.com/IQKV](https://github.com/IQKV) | **License**: MIT
