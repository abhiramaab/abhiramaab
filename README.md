<div align="center">

# Abhirama

Backend Developer · Building scalable, reliable distributed systems.

Distributed Systems • Backend Engineering • Cloud Infrastructure

<p align="center">
  <a href="https://portfolio.abhiram.tech">Portfolio</a>
  ·
  <a href="https://linkedin.com/in/ababhirama">LinkedIn</a>
  ·
  <a href="https://x.com/abhiramcodes">X</a>
</p>

</div>

---

## Core Tech Stack

- **Architecture & System Design:** System Design (HLD & LLD), Idempotency, Distributed Mutex Locks, Transactional Outbox Pattern, Consistent Hashing, Double-Entry Ledger, Token-Bucket Rate Limiting
- **Languages & Frameworks:** Java (8/17/21), Spring Boot, Spring MVC, RESTful APIs, Microservices
- **Distributed & Data Stores:** PostgreSQL, MySQL, Redis, Spring Cloud (Eureka, Gateway, OpenFeign)
- **Security & Identity:** Spring Security, JWT, OAuth 2.0, RBAC
- **Cloud & Tooling:** Docker, AWS (EC2), Linux, Git, Maven, JUnit 5

---

## Open Source Contributions

- **[Apache Pulsar](https://github.com/apache/pulsar/pull/27022) (PR #27022 – Merged):** Prevent broker dispatch rate limiting overshoot under batched messages by dynamically scaling entry read limits using consumer batch estimates (`avgMessagesPerEntry`), preserving sub-batch forward progress, and handling uninitialized estimates before hash-range filtering (fixes #26959, merged into 5.1.0).
- **[Spring Boot (Core)](https://github.com/spring-projects/spring-boot) (`fix-netty-graceful-abort-hang-52119`):** Avoid hang in `NettyWebServer.stop()` when stopping immediately after graceful shutdown abort.
- **[Spring Cloud Config](https://github.com/spring-cloud/spring-cloud-config/pull/3272) (PR #3272 – Merged):** Azure DevOps Managed Identity passwordless authentication & Bearer token injection for JGit HTTP transport (+706 lines).
- **[Apache BifroMQ](https://github.com/apache/bifromq/pull/314) (PR #314 – Integrated via [#315](https://github.com/apache/bifromq/pull/315)):** Netty decoder buffer boundary alignment with MQTT varints & outbound packet size enforcement (Issue #313).
- **[Apache Shiro](https://github.com/apache/shiro/pull/2854) (PR #2854 – Merged into 3.0.1):** Microsoft Active Directory UPN vs DN principal binding fix in LDAP realm.
- **[Apache Camel Kamelets](https://github.com/apache/camel-kamelets/pull/3039) (PR #3039 – Merged):** Preserving `ce-kafkakey` across HTTP hops to maintain Kafka partition ordering.
- **[Spring Boot Admin](https://github.com/codecentric/spring-boot-admin/pull/5584) (PR #5584 – Merged):** Configurable browser notification timeouts & single-instance detail deep-linking (Issue #5504, +148 lines).
- **[Kestra Core Engine](https://github.com/kestra-io/kestra/pull/19007) (PR #19007 – Merged):** Socket descriptor leak fix during MCP auto health check probing.
- **[Kestra Telegram Plugin](https://github.com/kestra-io/plugin-telegram/pull/51) (PR #51 – Merged):** Case-sensitive `parseMode` enum validation to fail fast before API dispatch.
- **[Apache Hop Web](https://github.com/apache/hop/pull/8344) (PR #8344 – Merged):** Maintaining active `ServerPushSession` during pipeline log streaming to prevent UI freezes.
- **[Apache Hop Core](https://github.com/apache/hop/pull/8343) (PR #8343 – Merged):** Startup HTTP wire logging noise suppression in `HopEnvironment`.

---

## Featured Projects

### [LoomPay](https://github.com/abhiramaab/loompay) · [Live Demo](https://loompay.abhiram.tech)

High-throughput payment gateway orchestrator tackling race conditions, event delivery, and accounting.

- **Stack:** Java 21, Spring Boot 3, Redis, PostgreSQL, Docker, JUnit 5, Mockito
- **Links:** [Live Platform](https://loompay.abhiram.tech) · [Code](https://github.com/abhiramaab/loompay) · [Documentation](https://github.com/abhiramaab/loompay/blob/main/docs/ARCHITECTURE.md)

<details>
<summary><strong>System Design & Architecture Breakdown</strong></summary>

- **Idempotency & Distributed Locks:** Uses Redis `SET NX EX` with double-checked idempotency keys to guarantee payments are processed exactly once and prevent duplicate charges during concurrent clicks.
- **Transactional Outbox Pattern:** Writes payment events directly to an outbox table in the same database transaction, with a background worker relaying webhooks so messages never drop during network failures.
- **Double-Entry Ledger:** Records debits and credits for every transaction to keep account balances audit-proof.
- **Consistent Hashing Router:** Uses a 360° virtual node ring in memory (`TreeMap`) to balance merchant traffic across servers and handle node crashes cleanly.
- **Automated Reconciliation:** Runs a scheduled job to detect and fail out payments that got stuck in `PROCESSING` after 5 minutes.

</details>

---

### [Synoptiq](https://github.com/abhiramaab/synoptiq-docs) · [Live Demo](https://usesynoptiq.com)

Workspace automation and autonomous agent platform connecting Gmail, Google Calendar, GitHub, and unified search into one interface.

- **Stack:** Java 21, Spring Boot 3.5, Spring Security, PostgreSQL (Neon), OpenAI GPT-4.1-mini, Docker, AWS EC2, HTTP/2, React 18
- **Links:** [Live Platform](https://usesynoptiq.com) · [Documentation](https://github.com/abhiramaab/synoptiq-docs)

<details>
<summary><strong>System Design & Architecture Breakdown</strong></summary>

- **Deterministic Agent Router:** Uses an intent classifier to route structured queries directly (bypassing LLMs for sub-100ms response times) and delegates complex multi-step goals to an agent planner.
- **Parallel Tool Executor:** Executes external API requests across Gmail, Google Calendar, and GitHub concurrently using Java virtual threads and `CompletableFuture`.
- **Secure Token Lifecycle:** Encrypts multi-provider OAuth refresh tokens using AES-256 before database persistence and handles automatic token rotation without dropping active sessions.
- **Incremental Mailbox Sync:** Ingests changes using Gmail history tokens and delta updates instead of polling full mailboxes, saving network bandwidth and database write load.
- **Unified Semantic Search:** Consolidates queries across emails, thread attachments, GitHub PRs, and upcoming calendar meetings in one indexed pipeline.

</details>

---

### [RouteSphere](https://github.com/abhiramaab/RouteSphere) · [Live Demo](https://routesphere.abhiram.tech/)

Logistics and fleet dispatch management platform built for vehicle tracking, driver allocation, and operational control.

- **Stack:** Java 21, Spring Boot 3, Spring Data JPA, Spring Security, JWT, React, TypeScript, Tailwind CSS
- **Links:** [Live Platform](https://routesphere.abhiram.tech/) · [Code](https://github.com/abhiramaab/RouteSphere) · [Documentation](https://github.com/abhiramaab/RouteSphere/blob/main/docs/ARCHITECTURE.md)

<details>
<summary><strong>System Design & Architecture Breakdown</strong></summary>

- **Dispatch Orchestration:** State-driven trip transitions (`PENDING` -> `ASSIGNED` -> `IN_TRANSIT` -> `DELIVERED`) ensuring drivers and vehicles are never double-booked.
- **Fleet Telematics & Maintenance:** Logs vehicle operating metrics, fuel consumption ledgers, and scheduled preventative maintenance windows.
- **Automated Billing Engine:** Triggers customer freight invoice generation immediately upon delivery fulfillment with receipt dispatches.
- **Decoupled Security:** Enforces role-based access control (RBAC) and stateless HMAC-signed JWT filters separating drivers, dispatch coordinators, and financial auditors.

</details>

---

### [Velt](https://github.com/abhiramaab/velt) · [Live Platform](https://velt.cloud)

AI-native design generation platform synthesizing production-ready digital design documents, responsive prototypes, and design systems from natural language prompts.

- **Stack:** Java 21, Spring Boot 3.5, Next.js 15 (App Router), React 19, TypeScript, Tailwind CSS, Supabase, OpenAI GPT-4o
- **Links:** [Live Platform](https://velt.cloud) · [Code](https://github.com/abhiramaab/velt)

<details>
<summary><strong>System Design & Architecture Breakdown</strong></summary>

- **Strict Schema Enforcement:** Enforces deterministic OpenAI GPT-4o structured JSON schema outputs to guarantee compile-time type-safe design document trees.
- **Dual-Tier Service Layer:** High-performance Next.js 15 App Router frontend paired with an enterprise Java 21 / Spring Boot 3.5 backend service.
- **Automated Design Token Extraction:** Real-time generation of typography, color palette tokens, and CSS design variables directly from prompt synthesis.
- **Multi-Format Canvas Engine:** Dynamic rendering of responsive mobile, tablet, and desktop prototypes with live theme and layout adaptability.

</details>

---

## Currently Exploring

- Distributed Systems & High-Throughput Architecture
- System Design & Low-Level Design (LLD / HLD)
- Event-Driven Microservices (Kafka, RabbitMQ)
- Container Orchestration with Kubernetes

---

<div align="center">

Write clean code. Understand the system from first principles. Ship consistently.

</div>
