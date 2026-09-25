<div align="center">

# Abhirama

Self-Taught Backend Developer · Building scalable, reliable distributed systems.

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

- **[Spring Cloud](https://github.com/spring-cloud/spring-cloud-config/pull/3272) (Merged):** Implemented Azure DevOps Workload Identity authentication in Spring Cloud Config JGit HTTP transport (+706 lines).
- **[codecentric / spring-boot-admin](https://github.com/codecentric/spring-boot-admin/pull/5584) (Merged):** Configurable browser notifications timeout and click-through deep-linking to instance details for single-instance status changes (Issue #5504, +148 lines).
- **[Apache Camel](https://github.com/apache/camel-kamelets/pull/3039) (Merged):** Resolved Kafka record key preservation across HTTP hops in kafka-sink Kamelet.
- **[Apache Shiro](https://github.com/apache/shiro/pull/2854) (Merged):** Resolved Active Directory user principal name binding bug (merged in release 3.0.1).
- **[Apache Hop](https://github.com/apache/hop/pull/8344) (Merged):** Fixed Hop Web stalled session bug via ServerPushSession UI keepalive and suppressed redundant HTTP wire logs.
- **[Kestra](https://github.com/kestra-io/kestra/pull/19007) (Merged):** Fixed MCP client auto health-check socket leaks in core engine and added enum validation for Telegram plugin.
- **[Jenkins](https://github.com/jenkinsci/atlassian-jira-software-cloud-plugin/pull/143):** Resolved URL percent-encoding in Jira Cloud plugin; eliminated workspace polling in Workflow SCM Step plugin.

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

## Currently Exploring

- Distributed Systems & High-Throughput Architecture
- System Design & Low-Level Design (LLD / HLD)
- Event-Driven Microservices (Kafka, RabbitMQ)
- Container Orchestration with Kubernetes

---

<div align="center">

Write clean code. Understand the system from first principles. Ship consistently.

</div>
