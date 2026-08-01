## 🚀 iQ Key Value Platform

> Production-ready **Hybrid Tenancy** SaaS foundation. One codebase for multi-tenant B2B or single-tenant B2C applications.

[![Project Site](https://img.shields.io/badge/Project-iqkv.dev-blue?style=for-the-badge&logo=appveyor)](https://iqkv.dev)
[![Live Demo](https://img.shields.io/badge/Demo-iqkv.site-success?style=for-the-badge&logo=playstation)](https://iqkv.site)

<div align="center">
  <img src="https://github.com/dimdnk/dimdnk/blob/dev/screenshots/chrome_IS8q0S3OwG.gif?raw=true" width="800" alt="IQKV Platform — Tenant App + Platform Admin">
  <p><strong>Hybrid Tenancy SaaS Boilerplate</strong></p>
</div>

**[Microservices Platform](https://github.com/IQKV/microservices-platform)** - Core backend (IAM, Gateway, Billing, CMS, Audit) + Production React SPAs.

**Tech Stack**: Java **25** + Spring Boot **4.1**, React **19** + TypeScript **6** + Mantine **9**, PostgreSQL **17**, RabbitMQ, Astro  
**Key Features**: Hybrid Tenancy, JWT RS256, OAuth2/OIDC Federation, Stripe + Lemon Squeezy, Schema-per-tenant, Audit Logs, Notifications, FSD Architecture  
**Deployment**: Kubernetes + Helm, Docker, Drone CI/CD 10-stage pipeline  
**Links**: [iqkv.dev](https://iqkv.dev) | [iqkv.site](https://iqkv.site) | [app.iqkv.site](https://app.iqkv.site) | [admin.iqkv.site](https://admin.iqkv.site) | Apache 2.0

<details>
<summary><strong>💼 Business & UI Capabilities</strong></summary>

**👥 Identity & Access (IAM)**

- Hybrid Tenancy: Multi-tenant (B2B) or Single-tenant (B2C) rollout modes
- Self-service signup, invitation flows, and 2-layer token revocation (JTI denylist + global signout)
- RBAC with `TENANT_OWNER`, `ADMIN`, `MEMBER`, and `PLATFORM_ADMIN`
- **OAuth2/OIDC Federation**: Social login via Google, GitHub, and Microsoft; account linking/unlinking
- **Enterprise SSO**: Tenant-scoped custom OIDC provider configuration with AES-256-GCM encrypted secrets
- **Magic Link Auth**: Passwordless sign-in with configurable TTL and rate limiting
- **Token Exchange**: Seamless workspace switching without re-authentication
- **Avatar Uploads**: Two-phase presigned S3/MinIO flow with auto-cleanup
- **In-App Notifications**: Real-time WebSocket/STOMP push + persisted unread badges
- **Global Announcements**: Multi-lingual with async fan-out to all users

**💳 Billing & Payments**

- **Dual payment gateway**: Stripe and Lemon Squeezy — runtime configurable via a single property
- **Two pricing models**: `FLAT` (fixed price) and `PER_SEAT` (per-user billing with seat count enforcement)
- Plan catalog management via YAML config; idempotent normalized webhook processing for both gateways
- **Plan Feature Enforcement**: `plan_code` JWT claim propagated through Gateway; `PlanFeatureGuard` annotation; HTTP 402 on quota or feature violations
- Entitlement evaluation with typed quotas (`maxUsers`, `maxProjects`) and open feature map
- **Refunds API**: Full refund management for tenants and platform admin
- **Customer Portal**: Self-service billing management (both Stripe and Lemon Squeezy)
- Trial period support with `isInTrial` and `trialDaysLeft` on subscription responses

**📱 Included UI Applications**

- **Tenant App**: React 19 SPA — workspace members (team management, billing self-service, notifications, connected accounts, SSO configuration, i18n: en/bg/de/fr)
- **Platform Admin**: Operator console — global user/org management, subscriptions, audit logs, announcements, refunds, user identity management (i18n: en/bg/de/fr)
- **Landing Kit**: Performance-optimized Astro site with auth-aware navigation, plan selector with per-seat pricing support

</details>

<details>
<summary><strong>🏗️ Architecture & Implementation</strong></summary>

**Backend Services** (100+ REST endpoints, 20+ domain event types):
- **IAM Service**: Auth / Tenancy / OAuth2-OIDC / Invitations / Announcements / Notifications / Magic Link
- **Gateway Service**: Spring Cloud Gateway (WebFlux) / RS256 JWT validation / Header sanitization / Plan enforcement / Audit context propagation
- **Billing Service**: Payments / Subscriptions / Seat management / Refunds / Dual gateway (Stripe + Lemon Squeezy)
- **Audit Service**: Passive event-driven audit logs; SPI pattern; JSONB metadata; severity filtering
- **CMS Service**: Content management, multi-language support, hierarchical pages, SEO metadata

**Frontend SPAs** (60+ UI routes): Feature-Sliced Design (FSD), TanStack Router/Query, Zustand, Lingui 6 i18n, React Hook Form + Zod, Vitest + Playwright, OxLint / OxFmt

**Infrastructure**: PostgreSQL 17 (schema-per-tenant isolation), RabbitMQ (topic exchange, DLQ), Redis (OAuth2 PKCE state, token denylist), MinIO S3, Prometheus + Grafana + Loki, Helm / Kubernetes

**Technical Standards**:

- **Backend**: Domain-driven design, MyBatis schema routing, ShedLock scheduled jobs, Micrometer custom metrics
- **Security**: PKCE OAuth2 flow, header sanitization, JTI denylist, brute-force lockout, JWKS, BCrypt strength 12
- **Observability**: Prometheus metrics on all services, pre-provisioned Grafana dashboards (JVM, IAM, Gateway, Billing, Audit), structured JSON logging with correlation ID
- **Quality**: SonarQube, JaCoCo 80% gate, PMD, SpotBugs, ArchUnit, Testcontainers
- **Operations**: Multi-stage Docker builds (JDK build → JRE runtime, non-root), semantic versioning, automated changelogs, HPA (2–10 replicas)

**Platform Numbers**:
- **5** backend services · **3** frontend applications · **2** shared libraries
- **2** deployment modes (MULTI_TENANT / SINGLE_TENANT) with zero-migration path
- **2** payment gateways (Stripe + Lemon Squeezy)
- **3** social login providers (Google, GitHub, Microsoft)
- **4** PostgreSQL databases with schema-per-tenant in IAM and CMS

</details>
