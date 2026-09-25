<div align="center">

# Abhirama

Building scalable, reliable backend and distributed systems.

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

- **Architecture & System Design:** System Design (HLD & LLD), Distributed Mutex Locks, Transactional Outbox Pattern, Consistent Hashing, Double-Entry Ledger, Token-Bucket Rate Limiting
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

### [Synoptiq](https://github.com/abhiramaab/synoptiq)

A productivity platform backend that aggregates workspace services into automated workflows.

- **Stack:** Java, Spring Boot, Spring Security, PostgreSQL, Docker, AWS EC2, HTTP/2
- Engineered Google OAuth 2.0 sync (Gmail API), HTTP/2 multiplexing, real-time Server-Sent Events (SSE), and stateless JWT filter chains.

---

### [LoomPay](https://github.com/abhiramaab/loompay) · [Live Demo](https://loompay.abhiram.tech)

A high-throughput distributed payment and ledger orchestration engine engineered for zero-loss financial transaction processing.

- **Live Platform:** [loompay.abhiram.tech](https://loompay.abhiram.tech) · **Code:** [github.com/abhiramaab/loompay](https://github.com/abhiramaab/loompay)
- **Stack:** Java 21, Spring Boot 3, Redis, PostgreSQL, Docker, System Design, JUnit 5, Mockito
- **System Design Core:**
  - **Distributed Mutex Lock:** Eliminates double-charging under concurrent payment bursts using atomic Redis `SET NX EX` locks with Double-Checked Idempotency.
  - **Transactional Outbox Pattern:** Guarantees zero-loss event and webhook dispatching under the same ACID transaction without distributed 2PC overhead.
  - **Double-Entry Ledger:** Enforces financial integrity with strict debit/credit balance pairing.
  - **Consistent Hashing Router:** Implements 360° ring routing with virtual replicas to eliminate node hotspots and handle server failures gracefully.
  - **Automated Reconciliation:** Background scheduler rescuing stuck `PROCESSING` transactions via automated timeouts.

---

### [RouteSphere](https://github.com/abhiramaab/RouteSphere) · [Live Demo](https://routesphere.abhiram.tech/)

A logistics and route dispatch management platform built for fleet tracking, driver allocation, and operational control.

- **Live Platform:** [routesphere.abhiram.tech](https://routesphere.abhiram.tech/)
- **Stack:** Java 21, Spring Boot 3, Spring Data JPA, Spring Security, JWT, React, TypeScript, Tailwind CSS
- Provides automated shipment tracking across national freight corridors, driver allocation, vehicle telematics, and automated invoicing.

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
