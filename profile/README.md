## 🚀 IQ Key Value Platform

> Production-ready **Hybrid Tenancy** SaaS foundation. One codebase for multi-tenant B2B or single-tenant B2C applications.

[![Project Site](https://img.shields.io/badge/Project-iqkv.dev-blue?style=for-the-badge&logo=appveyor)](https://iqkv.dev)
[![Live Demo](https://img.shields.io/badge/Demo-iqkv.site-success?style=for-the-badge&logo=playstation)](https://iqkv.site)

**[Microservices Platform](https://github.com/IQKV/microservices-platform)** - Core backend (IAM, Gateway, Billing) + Production React SPAs.

**Tech Stack**: Java **25** + Spring Boot **4.x**, React **19** + Mantine, PostgreSQL, RabbitMQ, Astro  
**Key Features**: Hybrid Tenancy, JWT RS256, Stripe, Schema-per-tenant, FSD Architecture  
**Deployment**: Kubernetes + Helm, Docker, Drone CI/CD 10-stage pipeline  
**Links**: [iqkv.dev](https://iqkv.dev) | [iqkv.site](https://iqkv.site) | [iqkv.com](https://iqkv.com) | Apache 2.0

<details>
<summary><strong>💼 Business & UI Capabilities</strong></summary>

**👥 Identity & Access (IAM)**
- Hybrid Tenancy: Multi-tenant (B2B) or Single-tenant (B2C) rollout modes
- Self-service signup, invitation flows, and 2-layer token revocation
- RBAC with `TENANT_OWNER`, `ADMIN`, `MEMBER`, and `PLATFORM_ADMIN`

**💳 Billing & Payments**
- Stripe-backed subscriptions with automated customer provisioning
- Plan catalog management and idempotent webhook processing
- Entitlement evaluation for feature access control

**� Included UI Applications**
- **Tenant App**: React 19 SPA for workspace members (team, account, signup)
- **Platform Admin**: Operator console for global user/org management and metrics
- **Landing Kit**: Performance-optimized Astro site for product marketing

</details>

<details>
<summary><strong>🏗️ Architecture & Implementation</strong></summary>

**Backend Services**: IAM Service (Auth/Tenancy), Gateway Service (Reactive/Security), Billing Service (Payments)

**Frontend SPAs**: Feature-Sliced Design (FSD), TanStack Router/Query, Lingui i18n, Vitest/Playwright

**Infrastructure**: PostgreSQL 17 (schema isolation), RabbitMQ (event-driven), Traefik, Helm

**Technical Standards**:
- **Backend**: Domain-driven design, MyBatis schema routing, ShedLock, Micrometer
- **Security**: Header sanitization, JTI denylist, brute-force lockout, JWKS
- **Quality**: SonarQube, PMD, SpotBugs, ArchUnit, Testcontainers
- **Operations**: Multi-stage Docker builds, semantic versioning, automated changelogs

</details>

