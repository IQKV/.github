## 🚀 IQ Key Value Platform

> Production-ready **Hybrid Tenancy** SaaS foundation. One codebase for multi-tenant B2B or single-tenant B2C applications.

[![Project Site](https://img.shields.io/badge/Project-iqkv.dev-blue?style=for-the-badge&logo=appveyor)](https://iqkv.dev)
[![Live Demo](https://img.shields.io/badge/Demo-iqkv.site-success?style=for-the-badge&logo=playstation)](https://iqkv.site)

<div align="center">
  <img src="https://github.com/dimdnk/dimdnk/blob/dev/screenshots/chrome_IS8q0S3OwG.gif?raw=true" width="800" alt="IQKV Platform — Tenant App + Platform Admin">
  <p><strong>Hybrid Tenancy SaaS Boilerplate</strong></p>
</div>

**[Microservices Platform](https://github.com/IQKV/microservices-platform)** - Core backend (IAM, Gateway, Billing, CMS, Audit) + Production React SPAs.

**Tech Stack**: Java **25** + Spring Boot **4.x**, React **19** + Mantine, PostgreSQL, RabbitMQ, Astro  
**Key Features**: Hybrid Tenancy, JWT RS256, Stripe, Schema-per-tenant, Audit Logs, Notifications, FSD Architecture  
**Deployment**: Kubernetes + Helm, Docker, Drone CI/CD 10-stage pipeline  
**Links**: [iqkv.dev](https://iqkv.dev) | [iqkv.site](https://iqkv.site) | [iqkv.com](https://iqkv.com) | Apache 2.0

<details>
<summary><strong>💼 Business & UI Capabilities</strong></summary>

**👥 Identity & Access (IAM)**

- Hybrid Tenancy: Multi-tenant (B2B) or Single-tenant (B2C) rollout modes
- Self-service signup, invitation flows, and 2-layer token revocation
- RBAC with `TENANT_OWNER`, `ADMIN`, `MEMBER`, and `PLATFORM_ADMIN`
- **Token Exchange**: Seamless tenant switching without re-authentication
- **Avatar Uploads**: Two-phase presigned S3/MinIO flow with auto-cleanup
- **In-App Notifications**: Real-time WebSocket push + persisted unread badges
- **Global Announcements**: Multi-lingual with async fan-out to all users

**💳 Billing & Payments**

- Stripe-backed subscriptions with automated customer provisioning
- Plan catalog management and idempotent webhook processing
- Entitlement evaluation for feature access control
- **Refunds API**: Full refund management for tenants, platform admin overview
- **Stripe Customer Portal**: Self-service billing management

**📱 Included UI Applications**

- **Tenant App**: React 19 SPA for workspace members (team, account, signup, billing, notifications)
- **Platform Admin**: Operator console for global user/org management, metrics, audit logs, announcements, and refunds
- **Landing Kit**: Performance-optimized Astro site for product marketing

</details>

<details>
<summary><strong>🏗️ Architecture & Implementation</strong></summary>

**Backend Services**:
- **IAM Service**: Auth/Tenancy/Invitations/Announcements/Notifications
- **Gateway Service**: Reactive/Security/Audit Context/Metrics
- **Billing Service**: Payments/Subscriptions/Refunds
- **Audit Service**: Centralized event-driven audit logs with SPI
- **CMS Service**: Content management, multi-language support, hierarchical content

**Frontend SPAs**: Feature-Sliced Design (FSD), TanStack Router/Query, Lingui i18n, Vitest/Playwright

**Infrastructure**: PostgreSQL 17 (schema isolation), RabbitMQ (event-driven), Traefik, Helm, Prometheus+Grafana

**Technical Standards**:

- **Backend**: Domain-driven design, MyBatis schema routing, ShedLock, Micrometer
- **Security**: Header sanitization, JTI denylist, brute-force lockout, JWKS
- **Observability**: Prometheus metrics, Grafana dashboards, structured logging
- **Quality**: SonarQube, PMD, SpotBugs, ArchUnit, Testcontainers
- **Operations**: Multi-stage Docker builds, semantic versioning, automated changelogs

</details>
